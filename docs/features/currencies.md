# Currencies

Currencies are distributed through [prompts](prompts.md) and can be used to purchase [items](items.md) from [shops](shops.md), as well as attached to [character design updates](design-updates.md). They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md).

## Usage

Currencies owned by a user can be viewed from their user profile and public bank. Users can transfer currency from their bank (provided that currency can be transferred).

Currencies can be obtained via the following methods:

- Prompt rewards/Claims
- Box type items
- Transferred/traded from another user
- Granted by users with the **Edit Inventories** [power](user-ranks.md), in the admin panel

Currencies can be spent/removed via the following methods:

- Used to purchase from shops
- Attached to design updates
- Transferred/traded to another user
- Removed by users with the **Edit Inventories** [power](user-ranks.md), in the admin panel

Removal can be done using the grant currency feature by entering a negative value. Users cannot own negative currency.

A log of ingoing/outgoing currencies can be found on the user's bank pages.

## Editing

Currencies have the following properties:

- Currency Name
- Abbreviation
- Icon Image
- World Page Image
- Description (accepts HTML)
- Attach to Users
    - Profile Display
    - User → User Transfers
- Attach to Characters
    - User → Character Transfers
    - Character → User Transfers

**Currency Name** is the currency's full name (e.g. "Gold") that is displayed on the encyclopedia and bank pages. It is also shown in dropdown selections.

**Abbreviation** is the short form of the currency's name (e.g. "G"). It is used if an icon is not provided, and also listed alongside the currency's full name in the bank. If an abbreviation is not provided, the currency's full name will be used instead.

The **Icon Image** is a small image that can be used to represent the currency (e.g. a gold coin). There is no restriction on the size of the image, but the recommended height is 16 pixels. This image is displayed on the user's profile page as well as in logs.

The **World Page Image** is shown in the encyclopedia, and nowhere else. As with all encyclopedia images, the recommended size is 200 x 200 pixels, but can be any size.

**Description** is a description of the currency for the encyclopedia page.

The **Attach to Users** option allows users to hold this currency. Similarly, the **Attach to Characters** option allows characters to hold this currency. Either of these options must be selected.

The **Profile Display** option chooses whether or not to display the currency on the user's profile, making it easy to tell how much currency the user is holding at a glance. The user's other currencies can still be viewed easily from their bank page. This makes it possible to, for example, give users event currencies without it showing prominently on their profiles when the event is not running.

The **User → User Transfers**, **User → Character Transfers** and **Character → User Transfers** concern whether currencies can be transferred in those directions. Note that character-to-character transfers are not an option as this is achievable by selecting both the user/character transfer options. Disabling the user-to-user option also prevents currencies from being attached to trades.

Additionally, the display order of currencies can be edited from the Sort Currencies page. This order affects how currencies are displayed on profiles and in the bank, and user-owned currencies and character-owned currencies can have different sorting orders.

## See Also

- [Shops](shops.md)