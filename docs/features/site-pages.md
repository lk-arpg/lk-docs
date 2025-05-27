# Site Pages

Site pages are dynamically created pages that can be created and edited in the admin panel (requires the **Edit Pages** [power](user-ranks.md)).

## Editing

Pages require a title, unique key, content and viewable setting. Each page can be accessed from `(site-url)/info/{key}`, which displays the title, date of creation, date of last update and content, assuming that the page is set to viewable.

Page content can contain HTML, but cannot contain Javascript.

## Default Pages

A few default pages are added during setup. These pages cannot be deleted, but are otherwise editable the same way (title and key can be edited).

These pages are:

- About
- Privacy Policy
- Terms of Service

## See Also

- [Site Settings](site-settings.md)
- [News](news.md)