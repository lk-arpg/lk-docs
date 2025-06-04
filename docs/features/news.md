# News

News are a form of text post that can be used to alert all users to important information. They can be edited in the admin panel by users with the **Edit Text Pages** [power](user-ranks.md).

## Usage

News posts can be created in the admin panel and viewed on the news page. The news page lists news posts ordered by newest first. When a new post is made, all users will gain an alert at the top of every page notifying them of the new post. This alert disappears when the news page is viewed.

News posts can be scheduled to post at certain times. Note that this posting is handled via crontab scheduling, and therefore may not be entirely accurate to the minute.

## Editing

News posts have the following properties:

- Title
- Post Time
- Post Content (accepts HTML)

**Title** is the title of the news post.

**Post Time** is optional, and schedules the post to be posted after a certain date/time. If not set, the news post will be posted immediately.

**Post Content** is the content of the news post itself. HTML is allowed. The [File Manager](file-manager.md) can be used to upload images to be inserted into news posts if desired.

## See Also

- [Site Pages](site-pages.md)
- [Sales](sales.md)