# User Accounts

User accounts are required to use most of the site's features, including participation through prompt submissions and managing owned characters. User data can be edited in the admin panel by users of a rank with the **Manage Users** [power](user-ranks.md).

## Registration

Users are able to register accounts by clicking on the Register button on the right side of the navigation bar when logged out. The name and e-mail address must be unique. An invitation key is required if the site is not open to new user signups.

New user accounts will always have FTO status on registration.

## Verification

After a new account has been created, users need to verify their identity by linking a social media or other platform (by default deviantArt) account to their site user account. They will not be able to use any other parts of the site until this process has been completed. Associated accounts' usernames are also referred to as the user's "aliases". Upon linkage, any characters that were previously credited an alias will be credited to the account immediately. This will also update their FTO status.

Users have a "primary" alias, which is always visible and is displayed on their profile, similar to the previous system. Users may also have multiple non-primary aliases. These may or may not be visible to other users, as set by the user. Which sites may or may not be used for authentication and/or as primary aliases can be configured in the sites [config file](config-files.md). Users may link and unlink additional accounts from any site(s) enabled at will so long as they retain a primary alias.

In the user admin panel, aliases cannot be changed directly but can be unlinked. Unlinking a user's primary alias will require the user to link an account again to regain access to their account features.

## Profile

Each user has a profile page, which lists their name, rank, join date, FTO status and other details. A summary of currencies, newest items in their inventory as well as their characters are displayed on the lower half of the page. Users have an HTML-compatible section of their page that they can edit from their user settings.

This profile page will also display an alert if the user has been banned.

From the main profile page, the sidebar includes links to logs of player activity, a list of their current aliases, as well as their [characters](characters.md), [bank](currencies.md), and [inventory](items.md).

Also included are links to the user's gallery-- automatically populated with any [gallery](galleries.md) submissions the user has made and/or collaborated on-- as well as to a list of gallery submissions the user has favourited and a special version of this page listing only favourites that also have one or more of the user's characters attached.

### FTO Status

This is a purely cosmetic status that adds a badge to the user's profile. Users are considered FTOs if they have had no logs of character ownership. This can be edited in the user admin panel manually.

MYO slots do not remove FTO status until they are submitted for design approval and successfully approved.

## Logs

Logs for the following are accessible from the user's profile:

- Ownership history - logs the characters that the user has sent/received
- Item logs - logs the items that the user has used/sent/received
- Currency logs - logs the currencies that the user has used/sent/received
- Prompt submissions - logs the submissions that the user has submitted (only approved submissions)

## Bans

Users can be banned from the admin panel. This still allows them to log in, but they can no longer participate in site activities and/or transfer assets to/from other users.

Banning causes a few things to happen immediately:

- Pending character transfers to/from the user are cancelled
- Pending gallery submissions from the user are rejected
- Pending prompt submissions and claims from the user are rejected
- Pending design update approvals/MYO approvals from the user are rejected
- Pending trades involving the user are rejected
- The user's rank is downgraded to the lowest possible rank

A ban reason can be attached to a ban. This is visible on the site's blacklist, although it is not listed directly on the user's profile.

## See Also

- [User Ranks](user-ranks.md)
- [Characters](characters.md)