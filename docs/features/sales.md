# Sales

Sales are a form of text post that can be used to alert all users to on-site sales, i.e. of adoptables. They can be edited in the admin panel by users with the **Edit Text Pages** [power](user-ranks.md).

## Usage

Sales posts can be created in the admin panel and viewed on the sales page. The sales page lists sales posts ordered by newest first. When a new post is made, all users will gain an alert at the top of every page notifying them of the new post. This alert disappears when the sales page is viewed.

Sales posts can be scheduled to post at certain times. Note that this posting is handled via crontab scheduling, and therefore may not be entirely accurate to the minute.

## Editing

Sales posts have the following properties:

- Title
- Post Time
- Post Content (accepts HTML)
- Is Open
- Comments Open At

**Title** is the title of the sales post.

**Post Time** is optional, and schedules the post to be posted after a certain date/time. If not set, the sales post will be posted immediately.

**Post Content** is the content of the sales post itself. HTML is allowed. The [File Manager](file-manager.md) can be used to upload images to be inserted into sales posts if desired.

**Is Open** controls whether the sales post is labeled (in the title) as "Open" or "Closed". This is entirely cosmetic. If Comments Open At is set and in the future, and the post is set as open, the the sales post will be labeled "Preview" instead of "Open".

**Comments Open At** is optional, and schedules when comments on the post become visible to users. If this is set, comments on the post will be hidden from users without editing permissions until the set time. Users with permissions, meanwhile, can see comments and may perform any needed set-up for a sale.

### Characters

[Characters](characters.md) can also be attached to sales posts, allowing for easy formatting and display of per-character sale information.

Characters attached to sales have the following properties:

- Character Code
- Sale Type & Associated Information
- Notes (no HTML)
- Link
- Is Open

**Character Code** refers to the character's unique identification code.

**Sale Type** allows the selection of the type of sale. The available options are:

- Flatsale
- Auction
- OTA
- XTA
- Raffle
- Flatsale Raffle
- Pay What You Want

Field(s) for additional information appropriate to the sale type become available on selection of a sale type. These are:

- Flatsale: Price
- Auction: Starting Bid, Minimum Increment, Autobuy (optional), End Point (optional)
- OTA/XTA: Autobuy (optional), End Point (optional), Minimum Offer (optional)
- Pay What You Want: Minimum Offer (optional)

**Notes** are optional; any brief notes about the character that are useful to display can be entered here.

The **Link** is optional; the link to  where the character may be bought, bid on, etc.

**Is Open** controls whether or not the individual character sale is displayed as open. Characters can be set closed independent of the sales post if it is open, but if the overall sales post is set closed, all characters attached are displayed as closed. This is wholly cosmetic.

Sales posts with attached characters are divided into separate sections (header, followed by character(s), followed by the standard body of the sales post). Each attached character is displayed in its own section, with sale type and info alongside info about the character, such as species and rarity. In the interest of archival, the character's first available/visible image is used in the event that a character receives design update(s) after being sold. If there is only one character associated with a sales post, the full image rather than thumbnail is displayed as well as the character's traits.

## See Also

- [News](news.md)
- [Site Pages](site-pages.md)
- [Characters](characters.md)