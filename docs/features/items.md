# Items

Items can be owned by [users](user-accounts.md) and may be used in various ways. They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md).

## Usage

Items can be created in the admin panel. Once created, they can be distributed to users through a variety of ways. Item categories are optional, but provide categorisation in the user's inventory and [shop](shops.md) pages.

Items are primarily used as turn-ins for character [design updates](design-updates.md). Depending on their item tags, they may also have additional functionality.

## Editing

### Categories

Editing item categories and items requires the **Edit World Data** power.

Item categories can be created in the admin panel, with the usual category properties:

- Name
- World Page Image
- Description (accepts HTML)

The image and description are displayed only on the world page. Categories are optional, but useful for sorting items. Items without a category will be placed in a "Miscellaneous" category in the inventory.

Additionally, categories can be sorted from the Item Categories index page. This order reflects the sorting order of categories in user inventories.

### Items

Items themselves have the following properties:

- Name
- World Page Image
- Item Category
- Description (accepts HTML)
- Allow User → User Transfer

**Name** is the item name which is displayed on the item index and shown in user inventories.

The **World Page Image** is shown in the encyclopedia, and also functions as the item's thumbnail image in inventories. As with all encyclopedia images, the recommended size is 200 x 200 pixels, but can be any size.

**Item Category** is the category to which the item falls under, and used for organisation. It is otherwise optional.

**Description** is a description of the item for the encyclopedia page.

**Allow User → User Transfer** is a setting for whether the item can be transferred to another user. This can be used to create account-bound items - items with this turned off cannot be sent to another user or added to a trade. Note that individual items can also be account-bound at the time of granting, so this setting does not have to be used if you want to create only selectively account-bound items.

### Item Tags

This is a section under the item editing form that becomes accessible after the item has been created. Item tags are special settings that affect how the item can be used from a user's inventory - what they do has to be written in the site code itself, but once coded, can be attached to any item to give them the special behaviour.

The Add a Tag button can be used to select an item tag. Duplicate item tags cannot be added to the same item. Attached item tags can be toggled on or off to allow or remove functionality without completely removing the item tag.

By default, the Box type item tag is available - this allows you to choose a particular set of rewards from items, currencies and loot tables. When a user chooses to use the item in the inventory, they will receive these rewards. The process of creating this item tag can be seen in [this tutorial](../guides/creating-item-types.md).

## Inventory

Each user has an inventory, which is sorted by item category and further sorted by alphabetical order of item names. Clicking on an item brings up a menu that lists the item's source (if any), accompanying notes (if any), and actions that can be performed on it.

The **Source** field notes down the source of the item. This field is automatically filled out when the user receives an item through site activity e.g. through [prompts](prompts.md)/[claims](claims.md) and functions as a record of how/why an item was received. In the case of shop purchases, this also notes who purchased the item, the shop it was purchased from, and the price.

The **Notes** field contains additional information about the item. This is sometimes automatically filled out - for example, purchasing an item from a shop will fill the Notes section with the date of purchase. When granting an item from the admin panel, staff can fill in this section with a custom message.

Below this section, actions that can be used are listed. Special actions from item tags are listed first, then general actions.

**Transfer Item** (if the item can be transferred) allows the user to transfer the item to another user.

**Delete Item** allows the users to trash the item entirely.

## See Also

- [User Accounts](user-accounts.md)
- [Shops](shops.md)
- [Tutorial: Creating Item Types](../guides/creating-item-types.md)