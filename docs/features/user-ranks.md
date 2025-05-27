# User Ranks

Ranks are assigned to users to manage their access to various parts of the site.

## Effects

Ranks have a name, description, colour, and can have any number (or none) of specific powers that restrict access to different parts of the admin panel. Users without the appropriate power will not be able to view certain admin pages/carry out certain actions. By default, the member rank has no powers, and therefore cannot access the admin panel at all. The colour assigned to a rank will be applied to the usernames of users of that rank.

The exception is the admin rank, which is created during setup. The admin rank cannot be deleted, its powers cannot be removed, and additionally has exclusive access to certain parts of the admin panel.

## Powers

Here is a complete list of powers and their descriptions.

#### Edit Site Settings

Allow rank to modify site settings and upload new images to replace the site layout images.

#### Edit World Data

Allow rank to modify the world data. This includes creating/editing/uploading images for species, items, traits, etc.

#### Edit Text Pages

Allow rank to create/modify text pages. This includes pages created using the page creator tool and news posts.

#### Manage Users

Allow rank to view/modify user account info and create invitation keys. This will grant access to the user admin panel.

#### Edit Ranks

Allow rank to change the rank of a user. This power requires the Edit User Info power to be attached as well.

#### Edit Inventories

Allow rank to grant and remove items from user inventories, as well as grant/remove currency from users and characters.

#### Manage Masterlist

Allow rank to create/edit new characters. This includes uploading new images, modifying traits on an existing character and forcing ownership transfers.

#### Manage Raffles

Allow rank to create/edit raffles, add/remove tickets for users and roll raffles.

#### Manage Submissions

Allow rank to view the submissions queue, edit rewards attached to a submission and approve/reject them.

## Editing

Ranks can be edited in the admin panel. **Only the admin rank is able to edit ranks - this is not an assignable power**.

Ranks can also be sorted - users will be sorted according to rank on the User Index, starting with the admin rank at the top. Lower ranks are also considered "weaker" than higher ranks - given 2 ranks that both have the Edit Ranks power, a lower-ranked user will not be able to edit the rank of the higher-ranked one.

The ranks of individual users can be assigned from the user admin panel.

## Admin

As mentioned above, the admin account has special access to certain pages and actions.

These include:

- User rank editing
- Viewing the blacklist when set to the greatest privacy level

## See Also

- [User Accounts](user-accounts.md)
- [Site Settings](site-settings.md)