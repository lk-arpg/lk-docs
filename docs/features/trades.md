# Trades

Trades are a method of securely transferring resources between 2 different user accounts.

## Usage

Current and past trades can be viewed by clicking "Trades" in the Activity menu. Trades can be created by clicking the New Trade button.

Each trade on the index lists the trade's status, sender's comment, each user's offer and the confirmation status. Only the two users involved as well as users with the **Manage Masterlist** power (as character transfers need to be able to be monitored) are able to view incomplete trades.

When a trade is completed and does not contain any characters, the assets will automatically be deposited into the other user's account. If the trade contains any characters, and the `open_transfers_queue` [site setting](site-settings.md) is set to 1, the trade will go into the transfers queue for approval. Otherwise, it will also complete automatically. Please see the [Characters](characters.md) article for more information on transfers.

Completed transfers can be viewed by any user. Cancelled and rejected transfers do not become visible to other users.

## Flow

### Trade Creation

Clicking on the New Trade button allows a user to initiate a trade with another user. The options are:

- Recipient
- Comments (Optional; no HTML, linebreaks are honoured)
- (Asset Selection)

The **Recipient** must be a registered user of the site.

**Comments** is a section where the sender can write a small note to the recipient. This can be used for stating the purpose of the trade.

**Asset Selection** comprises of 3 sections for selecting items from inventory, characters, and/or currency. Characters that cannot be transferred (cannot be gifted/traded/sold) are By default, a maximum of 20 things can be attached to one trade - this maximum can be edited in the [config files](config-files.md), however, it is recommended that this limit be kept low.

### Open Trade

In an open trade, each user is able to view both sides of the offer and edit/confirm their own offer. Both users must confirm their own offer, and then the entire trade after both offers have been confirmed, so that neither user is caught off-guard.

1. A edits A's offer and confirms. B edits B's offer and confirms.
2. A looks at A and B's offers and confirms trade. B looks at A and B's offer and confirms trade.
3. Trade is completed.

Offers can be unconfirmed if a user wants to change their offer. If a user wants to change their offer after the other user has confirmed the entire trade, the second user has to reconfirm after the first is done editing.

At this stage, the trade can be cancelled at any time. After the trade has been confirmed by both parties, it cannot be withdrawn.

### Approval

Approval is only required if the transfers queue is open and the trade contains at least one character. After confirmation, the trade will enter the transfers queue and be processed when approved by staff.

## See Also

- [Characters](characters.md)
- [User Accounts](user-accounts.md)
- [Items](items.md)
- [Currencies](currencies.md)