# Characters

Characters are a resource that can be attached to [user accounts](user-accounts.md). [MYO Slots](myo-slots.md) are "lesser" versions of characters with more restrictions on how they can be used with site features. They can be edited in the admin panel by users with the **Manage Masterlist** [power](user-ranks.md).

## Usage

All characters are listed on the [masterlist](masterlist.md).

Characters can hold [currency](currencies.md) and be used to participate in [prompts](prompts.md), as well as be transferred/traded. Their designs can be updated through the [design updates](design-updates.md) system. For more information, please refer to the respective pages.

Users are able to edit a section of their character's profile, and list their character as being available for receiving gift art and/or trade. This section also includes a text field that allows HTML.

## Editing

### Categories

Editing character categories requires the **Edit World Data** power.

Character categories can be created in the admin panel, with the following category properties:

- Name
- Code
- World Page Image
- Description (accepts HTML)

The image and description are displayed only on the world page.

The **Code** field is important for character code generation (covered below). This code should be unique among character categories, and preferably short.

Additionally, categories can be sorted from the Character Categories index page. This order reflects the sorting order of categories on the character categories encyclopedia page.

### Characters

Characters are set up in a manner such that traits, species, rarity and other specific details about the character tied to its current design are linked to [images](character-images.md) rather than the character itself. This allows the character to change and be updated, while preserving a record of previous forms (and the ability to revert to an earlier design) and/or have multiple approved forms for a character. This section will cover only the information attached to the character itself - for more information on character images, please see the [Character Images](character-images.md) page.

Characters have the following properties:

- Owner
- Owner Alias
- Character Category
- Number
- Character Code
- Description
- Is Visible
- Is Giftable
- Is Tradeable
- Is Resellable
- On Transfer Cooldown Until

The **Owner** is the user on-site who owns the character. This field can be left blank if the owner has not registered for an account, and the following field has been filled in.

The **Owner Alias** is the deviantART account name of the user who owns the character. If the Owner field is filled in, this field will be ignored. In the future, if the owner registers for the site, any characters listed under their deviantART name will automatically be attached to their account. Note that if the user has since changed their dA username, this will not happen (characters have to be transferred to their new site account manually).

The **Character Category** is required, and characters cannot be created if at least 1 character category does not exist yet. This is a category for the character that is separate from the character’s species or any other stats, and can be used for example to categorise creator-made designs, MYO designs and guest artist designs. Of course, the usage is entirely up to you - you can also use it to categorise characters by species, or any other criteria you see fit. This category, by default, provides the first half of the character code.

The **Number** is a second identifier for the character. This number can be automatically pulled for new characters, and the rule for how the number should be pulled can be found in the [config files](config-files.md). This number, by default, provides the second half of the character code.

The **Character Code** field automatically generates an identifier for the character based on the above two fields. This field **must** be unique among all characters, but otherwise can be edited in the form if desired. The default configuration generates codes that follow the {character category code}-{number} format, but this can be edited in the [config files](config-files.md). This code is used to access the character's page.

The **Description** field allows for a custom description to be entered. This can be left blank if no further information is required. Suggestions for content include: a link to the initial sales post for the character, additional conditions on the transfer of the character, any transfer cooldown, etc.

**Is Visible** controls whether the character is displayed on the character masterlist. If set to not visible, the character will only be visible to users with the Manage Masterlist power (even the owner cannot see it without the power).

**Is Giftable**, **Is Tradeable**, **Is Resellable** are toggles that display the respective information prominently on the character's profile. This is largely cosmetic as the site cannot tell what a character is being sold/traded for. However, the following effects will apply:

- If all toggles are off, the character is account-bound - it cannot be transferred by the user directly, and cannot be attached to [trades](trades.md). Only users with the Manage Masterlist power can force a transfer.
- If the character is not tradeable or resellable, the user will not be able to toggle the **Up For Trade** option in the character's profile (which is a searchable option on the masterlist).

**Resale Value** is a field that appears if the character is marked as resellable. The dollar value of the character can be set, which will be displayed on the character's profile. This is cosmetic, and purely for reference.

**On Transfer Cooldown Until** causes temporary account binding until the selected date/time. Until the cooldown time has been reached, the owner will not be able to directly transfer the character or attach it to a trade. It is possible to automatically set the cooldown date to x number of days (default: 3) when a user makes a transfer - please see [Site Settings](site-settings.md) for more information.

## User-editable Profile

After a character has been created, its profile can be edited by the owner or users with the Manage Masterlist power. The following properties can be modified by the user:

- Name
- Profile Content
- Allow Gift Art
- Up For Trade

**Name** is an optional name given to the character. This is purely cosmetic, and also displays next to the character's code on the masterlist, on user profiles, etc.

**Profile Content** is a section that allows HTML content to be entered.

**Allow Gift Art** is a toggle that denotes if the character's owner is open to receiving gift art of the character. This toggle can be searched on the [masterlist](masterlist.md) to find a list of characters for users to draw. This cannot be edited by anyone other than the owner.

**Up For Trade** is a toggle that denotes if the character's owner wants to trade the character. Similarly, this toggle can also be searched on the masterlist. This cannot be edited by anyone other than the owner.

Additionally, for users who are not the owner (has the required power), a **Notify User** toggle is present. If left on, the owner of the character will be notified that their character's profile has been edited (implied: for moderation purposes). Regardless of the status of the toggle, owners of non-visible characters will not be notified.

## Logs

Aside from images, characters have 4 types of logs: the change log, ownership history log, currency log and submission log.

**Change Log**: This log specifically logs changes to the character and its images. It lists the specific fields updated, who made the edits, as well as the date of editing.

**Ownership History**: This log tracks the transfer of the character between different users, noting the sender, recipient, log information as well as the date. This is similar to the ownership history log that a user also possesses, but specifically monitors the character only.

**Currency Logs**: Like the user currency logs, this log tracks the in and outflow of currency from the character's bank. Note that characters are unable to transfer currency between each other, and can only transfer currency to their owners. However, character-owned currencies can be used to purchase items from shops (if the settings allow).

**Submissions**: This is a list of submissions that the character has been attached to for rewards.

## Transfers

Characters may change hands in 3 ways:

- User-initiated transfer
- Staff-initiated transfer (a forced transfer)
- Trades

Transfers may be monitored by changing the `open_transfers_queue` [site setting](site-settings.md) to 1. This will place all character transfers and trades containing characters into a queue, and must be approved by a staff member before the transfer is completed.

User-initiated transfers are a unidirectional transfer from sender to recipient. The recipient is required to accept before they can receive the character. If the transfer queue is closed, the recipient will receive the character immediately upon accepting the transfer.

For trades, please see the [trades](trades.md) article.

## See Also

- [Character Images](character-images.md)
- [MYO Slots](myo-slots.md)
- [Masterlist](masterlist.md)
- [Trades](trades.md)
- [User Accounts](user-accounts.md)