# MYO Slots

MYO slots are a resource that can be attached to user accounts. MYO slots are "lesser" versions of [characters](characters.md) with more restrictions on how they can be used with site features - they are not considered full characters until they have been submitted for [design approval](design-updates.md) and approved. They can be edited in the admin panel by users with the **Manage Masterlist** [power](user-ranks.md).

## Usage

All MYO slots are listed on the MYO slot [masterlist](masterlist.md), which is separate from the character masterlist.

MYO slots cannot hold [currency](currencies.md) and cannot be used to participate in [prompts](prompts.md). If the gift/resale/trade options are configured to allow it, they can be transferred/traded. They can be converted into full characters through the [design updates](design-updates.md) system. For more information, please refer to the respective pages.

Users are able to edit a section of their MYO slot's profile, and list their character as being available for trade. This section also includes a text field that allows HTML.

## Editing

Similar to full characters, MYO slots are set up in a manner such that traits, species, rarity and other specific details about the character tied to its current design are linked to [images](character-images.md) rather than the MYO slot itself. When the MYO slot's design is approved, the record of its original conditions (rarity, species, required traits etc.) are preserved as an image. This section will cover only the information attached to the MYO slot itself - for more information on character images, please see the [Character Images](character-images.md) page.

MYO slots have the following properties:

- Name
- Owner
- Owner Alias
- Description
- Is Visible
- Is Giftable
- Is Tradeable
- Is Resellable
- On Transfer Cooldown Until

The **Name** is used on the MYO slot masterlist. As MYO slots do not have a category/number and character code yet, this name will be displayed on pages where the MYO slot is listed. This name is not editable by the owner. Using a descriptive name like "Rare MYO Slot" is recommended.

The **Owner** is the user on-site who owns the slot. This field can be left blank if the owner has not registered for an account, and the following field has been filled in.

The **Owner Alias** is the deviantART account name of the user who owns the slot. If the Owner field is filled in, this field will be ignored. In the future, if the owner registers for the site, any MYO slots listed under their deviantART name will automatically be attached to their account. Note that if the user has since changed their dA username, this will not happen (slots have to be transferred to their new site account manually).

The **Description** field allows for a custom description to be entered. This can be left blank if no further information is required. Suggestions for content include: specifics on how the slot was obtained, etc.

**Is Visible** controls whether the slot is displayed on the MYO slot masterlist. If set to not visible, the slot will only be visible to users with the Manage Masterlist power (even the owner cannot see it without the power).

**Is Giftable**, **Is Tradeable**, **Is Resellable** are toggles that display the respective information prominently on the slot's profile. This is largely cosmetic as the site cannot tell what a slot is being sold/traded for. However, the following effects will apply:

- If all toggles are off, the slot is account-bound - it cannot be transferred by the user directly, and cannot be attached to [trades](trades.md). Only users with the Manage Masterlist power can force a transfer.
- If the slot is not tradeable or resellable, the user will not be able to toggle the **Up For Trade** option in the slot's profile (which is a searchable option on the masterlist).

**Resale Value** is a field that appears if the slot is marked as resellable. The dollar value of the slot can be set, which will be displayed on the slot's profile. This is cosmetic, and purely for reference.

**On Transfer Cooldown Until** causes temporary account binding until the selected date/time. Until the cooldown time has been reached, the owner will not be able to directly transfer the slot or attach it to a trade. It is possible to automatically set the cooldown date to x number of days (default: 3) when a user makes a transfer - please see [Site Settings](site-settings.md) for more information.

## User-editable Profile

After a slot has been created, its profile can be edited by the owner or users with the Manage Masterlist power. The following properties can be modified by the user:

- Profile Content
- Up For Trade

**Profile Content** is a section that allows HTML content to be entered.

**Up For Trade** is a toggle that denotes if the slot's owner wants to trade the slot. Similarly, this toggle can also be searched on the masterlist. This cannot be edited by anyone other than the owner.

Additionally, for users who are not the owner (has the required power), a **Notify User** toggle is present. If left on, the owner of the slot will be notified that their slot's profile has been edited (implied: for moderation purposes). Regardless of the status of the toggle, owners of non-visible slots will not be notified.

## Logs

Unlike characters, MYO slots do not have an image gallery (new images cannot be uploaded until it becomes a full character) and have no submission/currency logs as they cannot be submitted in prompts/hold currency. MYO slots have only 2 types of logs: the change log and ownership history log.

**Change Log**: This log specifically logs changes to the slot and its images. It lists the specific fields updated, who made the edits, as well as the date of editing.

**Ownership History**: This log tracks the transfer of the slot between different users, noting the sender, recipient, log information as well as the date. This is similar to the ownership history log that a user also possesses, but specifically monitors the slot only.

## Transfers

MYO slots may change hands in 3 ways:

- User-initiated transfer
- Staff-initiated transfer (a forced transfer)
- Trades

Transfers may be monitored by changing the `open_transfers_queue` [site setting](site-settings.md) to 1. This will place all MYO slot transfers and trades containing slots into a queue, and must be approved by a staff member before the transfer is completed.

User-initiated transfers are a unidirectional transfer from sender to recipient. The recipient is required to accept before they can receive the slot. If the transfer queue is closed, the recipient will receive the slot immediately upon accepting the transfer.

For trades, please see the [trades](trades.md) article.

### Transfers Queue

The transfers queue has separate sections for transfers and trades; however, both work similarly. The contents of each transfer or trade can be reviewed by the staff member, and approved or rejected.

On clicking Approve, the staff member will have the option of adding a cooldown period (number of days) to each character involved. This field is prefilled with the default number in [site settings](site-settings.md) and can be modified to be more or less than the default, and applied immediately after approval. The transfer or trade is processed immediately after clicking Approve on this modal.

If the transfer is rejected, a comment can be added, which will be visible to the 2 users iinvolved.

## See Also

- [Characters](characters.md)
- [Character Images](character-images.md)
- [Masterlist](masterlist.md)
- [Trades](trades.md)
- [User Accounts](user-accounts.md)