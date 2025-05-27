# Tutorial: Creating Item Types

This is a tutorial on how to add new item types (item tags). Throughout the tutorial, I will also walk through the creation of the Box item type in the blue boxes, which was also implemented using this method.

!!! info "Following along with the 'box' item type..."

    First, let's define what a box type item is/does:

    - A box is an "openable" item. This item can be used from the inventory and will give the user a set of assets (can be defined in the admin panel), and delete the original item.
    - Assets can be items, currency or loot tables. Loot tables will be rolled. Multiple assets of various quantities can be attached in the admin panel.

## 1. Add item type to the config file

Find the config file: `config/lorekeeper/item_tags.php`

Add a row inside the array, in the format:

```php
'tag_name' => [
    'name' => 'Tag Name',
    'text_color' => '#000000',
    'background_color' => '#000000'
],
```

Where `text_color` and `background_color` are hexadecimal colour codes excluding the `#`. These colours will be used in displaying the tag label.

Replace `tag_name` and `Tag Name` as well, following those capitalisation/punctuation rules.

`tag_name` must be a unique key (all small letters, underscores instead of spaces), but `Tag Name` (any capitalisation, any formatting) does not have to be. The latter will be used in displaying tag names on user-facing pages.

!!! info "Following along with the 'box' item type..."

    Adding our box item type, which will be an orange tag label with white text.

    ```php
    'box' => [
        'name' => 'Box',
        'text_color' => '#ffffff',
        'background_color' => '#f6993f'
    ],
    ```

## 2. Add a service class for the item tag

This class will help us process the data and get relevant information for our form.

Create a file called `[ItemTag]Service.php` in `app/Services/Item`. The capitalisation is important!

These are the required functions:

- `getEditData()` - Retrieves any data that you need for your editing form. Should return an array, and can be accessed from the tag using $tag->getEditData().
- `getTagData($tag)` - Does some custom processing and returns tag data in an appropriate format for your needs. Can be accessed from the tag using $tag->getData(). This is not strictly necessary if you don't use it, but allows you to implement some custom handling.
- `updateData($tag, $data)` - Handles updating of the tag's data in the admin panel. Add your custom processing here.
- `act($stack, $user, $data)` - Handles what happens when a user uses the item.

??? abstract "Here is a blank template for the file:"

    ```php
    <?php namespace App\Services\Item;

    use App\Services\Service;

    class CustomService extends Service
    {
        /**
         * Retrieves any data that should be used in the item tag editing form.
         *
         * @return array
         */
        public function getEditData()
        {
            return [];
        }

        /**
         * Processes the data attribute of the tag and returns it in the preferred format.
         *
         * @param  string  $tag
         * @return mixed
         */
        public function getTagData($tag)
        {
            return [];
        }

        /**
         * Processes the data attribute of the tag and returns it in the preferred format.
         *
         * @param  string  $tag
         * @param  array   $data
         * @return bool
         */
        public function updateData($tag, $data)
        {
            return true;
        }

        /**
         * Acts upon the item when used from the inventory.
         *
         * @param  \App\Models\User\UserItem  $stack
         * @param  \App\Models\User\User      $user
         * @param  array                      $data
         * @return bool
         */
        public function act($stack, $user, $data)
        {
            return true;
        }
    }
    ```

You can also add any additional functions that you may need in order to process the data.

!!! info "Following along with the 'box' item type..."

    As we haven't started creating the form, we probably aren't entirely sure what data we'll need at this point, so we will just create `app/Services/Item/BoxService.php` for now and move on to the next step.

## 3. Add item tag settings editing to the admin panel

We need to create a form in the admin panel so we can edit the item data.

Go to the admin panel for the item you want to tag (`your-site-url.com/admin/data/items/edit/[item_id]`), and add the item tag you want to edit in the Item Tags section. Doing so should bring you to the tag settings page, but only the "Active" toggle will be visible. If you only want this tag to be cosmetic, you can stop here.

Add a new file in `resources/views/admin/items/tags` named `[tag_name].blade.php`, where `[tag_name]` is as you specified in the config file (no square brackets). This will contain the form HTML for our other fields.

A few other optional sections can be added to allow you to insert data into the page in various locations.

- If you're using Javascript, make a new file in `resources/views/js/admin_items` with the same file name as above and include script tags when writing your Javascript.
- Files can be added in `resources/views/admin/items/tags` named `[tag_name]_pre.blade.php` and `[tag_name]_post.blade.php`. These add content before and after the form respectively, so any form elements in these sections will not be sent along with the rest of the data.

!!! info "Following along with the 'box' item type..."

    We'll add 3 files:

    - `box.blade.php` in `resources/views/admin/items/tags`
    - `box_post.blade.php` in `resources/views/admin/items/tags`
    - `box.blade.php` in `resources/views/js/admin_items`

    As they rely heavily on pre-existing code, I would recommend going through the files to see how they're set up.

    These contain the code that will allow us to select assets using Javascript. The code in these files is fairly simple as I've made selectors that are easy to include.

    However, for the select inputs, we need to be able to retrieve the item/currency/loot table data to fill them out, so we'll do that in `BoxService`:

    - In `getEditData()`, we add the code to retrieve our dropdown data. This makes it possible to select assets from the form.
    - In `getTagData()`, we take the data attribute of the tag and format it so that our item/currency/loot table selection code can read it and show us what we've already put in the box.
    - In `updateData($tag, $data)`, we add the code that processes the data from the admin panel. This is where we handle the saving of what goes into the box.
    - In `act($stack, $user, $data)`, we add the code for distributing the box's contents and deleting the item from the user's inventory. This will be handled later.

## 4. Add front-facing views

Now that we're done with editing the item in the admin panel, let's look at how the user will see and interact with the item.

If you look at the item in your inventory (click on it to show the modal), you will see that it now displays the tag under the name. Let's add a new feature above the "Transfer Item" and "Delete Item" options.

Create a file named `_[tag_name].blade.php` (note the underscore in front) in `resources/views/inventory`. Add any additional options to the list in this file. Sample code:

```html
<li class="list-group-item">
    <a class="card-title h5 collapse-title"  data-toggle="collapse" href="#customForm"> Action Name</a>
    {!! Form::open(['url' => 'inventory/act/'.$stack->id.'/'.$tag->tag, 'id' => 'customForm', 'class' => 'collapse']) !!}
        <!-- You can add more form fields in this space. -->
        <div class="text-right">
            {!! Form::submit('Action Name', ['class' => 'btn btn-primary']) !!}
        </div>
    {!! Form::close() !!}
</li>
```

Some notes:

- IDs must be unique, so to avoid any overlap, change customForm (in both places) to a unique name.
- The above form only adds one new option on the modal, but you can add multiple by adding more in succession. The form URL must be the same, but you can distinguish the intended action by, for example, giving the submit button in each form a different name attribute.
- The action will only be displayed if the user is logged in and either owns the item, or is a staff member with the edit_inventories power.

!!! info "Following along with the 'box' item type..."

    As no other information is required in the form, we'll simply put in a note to the user that this action is irreversible. This functions as a confirmation screen for using the item.

    ```html
    <li class="list-group-item">
        <a class="card-title h5 collapse-title"  data-toggle="collapse" href="#openBoxForm"> Open Box</a>
        {!! Form::open(['url' => 'inventory/act/'.$stack->id.'/'.$tag->tag, 'id' => 'openBoxForm', 'class' => 'collapse']) !!}
            <p>This action is not reversible. Are you sure you want to open this box?</p>
            <div class="text-right">
                {!! Form::submit('Open', ['class' => 'btn btn-primary']) !!}
            </div>
        {!! Form::close() !!}
    </li>
    ```

## 5. Add action processing

We now need to write the back-end code for handling what happens when you use the item.

Back in `[ItemName]Service.php` from step 3, one of the functions we created was `act($stack, $user, $data)`. Inside that function, if you have only one possible action, you can directly write the handling code. If you have multiple possible actions, you can write a switch/case statement that checks $data and calls a different function depending on the intended usage.

Note that `$stack` refers to the user-held item stack, while `$stack->item` refers to the actual item data itself.

!!! info "Following along with the 'box' item type..."

    We don't want any other user except for the owner to open a box, so the first thing we do is check that the box belongs to the owner. Following that, we remove the box and distribute the associated rewards (with logging).

    ```php
    public function act($stack, $user, $data)
    {
        DB::beginTransaction();
    
        try {
            // We don't want to let anyone who isn't the owner of the box open it,
            // so do some validation... 
            if($stack->user_id != $user->id) throw new \Exception("This item does not belong to you.");
    
            // Next, try to delete the box item. If successful, we can start distributing rewards.
            if((new InventoryManager)->debitStack($stack->user, 'Box Opened', ['data' => ''], $stack)) {
    
                // Distribute user rewards
                if(!$rewards = fillUserAssets(parseAssetData($stack->item->tag('box')->data), $user, $user, 'Box Rewards', [
                    'data' => 'Received rewards from opening <a href="#" class="inventory-log-stack" data-id="'.$stack->id.'" data-name="'.$stack->item->name.'">'.$stack->item->name.'</a>'
                ])) throw new \Exception("Failed to open box.");  
            }
    
            return $this->commitReturn(true);
        } catch(\Exception $e) { 
            $this->setError('error', $e->getMessage());
        }
        return $this->rollbackReturn(false);
    }
    ```

## Summary

The whole process consists of 5 steps:

1. Adding the tag to `config/lorekeeper/item_tags.php`
2. Creating the service class in `app/Services/Item` containing 4 functions, `getEditData()`, `getTagData($tag)`, `updateData($tag, $data)` and `act($stack, $user, $data)`
3. Adding item tag setting form fields in `resources/views/admin/items/tags` and possibly `resources/views/js/admin_items` for the admin panel, and handling in service class if not already done
4. Adding action(s) to the inventory menu in `resources/views/inventory`
5. Adding the effects of inventory actions in the service class