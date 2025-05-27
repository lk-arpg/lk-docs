# Raffles

Raffles can be managed on the site with a feature that tracks tickets and rolls consecutive raffles automatically. They can be edited and rolled in the admin panel by users with the **Manage Raffles** [power](user-ranks.md).

## Usage

Raffles can be rolled one-by-one, or in groups. When an entire raffle group is rolled, the raffles in the group are rolled in order, and any winners removed from later raffles. Raffles cannot be rerolled, and do not automatically distribute prizes.

The raffle page lists all raffles, grouped by raffle groups, with non-grouped raffles at the top of the list. Each raffle can be clicked to view the raffle’s tickets.

On the individual raffle page, the raffle name, number of winners, number of tickets and paginated list of tickets are listed. If the user is logged in, they will also see how many tickets they hold, and if winners have been drawn, a table of winners is also displayed.

Tickets can be credited to both on-site users as well as deviantART users by username (alias). One user can have multiple tickets; each ticket counts as a single chance in the raffle. Each ticket has an equal chance to be rolled.

In the admin panel, when a raffle is clicked, the site will display the tickets entered in the raffle for editing. Tickets are displayed 200 to a page and numbered consecutively. The number is not bound to the ticket and can change when tickets are deleted, so there will not be any skipping of numbers.

## Editing

### Raffle Groups

Raffle groups have the following properties:

- Group Name
- Active

**Group Name** is the name of the raffle group. This name does not have to be unique.

The **Active** setting controls if the raffle group is visible to users.

### Raffles

Raffles have the following properties:

- Raffle Name
- Number of Winners to Draw
- Raffle Group
- Raffle Order
- Active

**Raffle Name** is the name of the raffle. This name does not have to be unique.

**Number of Winners to Draw** is the number of winning tickets to draw. The same user cannot win the same raffle twice. In the event that there are fewer unique users in the raffle than winners drawn, only the number of unique users will be drawn.

**Raffle Group** is the group that the raffle is grouped under.

**Raffle Order** is the order in which the raffle will be drawn, if the raffle is part of a group that will be rolled together. The lower the number, the earlier it will be drawn - e.g. a raffle numbered 1 will be drawn before a raffle numbered 2, and so on.

The **Active** setting controls if the raffle is visible to users.

#### Tickets

The ticket index allows adding tickets with a single text field:

- Names

**Names** should be entered into this field, separated by commas. Spaces will be removed. 1 name counts for 1 ticket, and duplicates of the same name can be entered to give the same user multiple tickets. These names will first be matched to usernames on the site, and if no match is found, it will label the ticket with the deviantART account of that name.

## See Also

- [User Accounts](user-accounts.md)
- [How Random is Random?](randomness.md)