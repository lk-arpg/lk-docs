# Release Notes

## Versioning Scheme

Lorekeeper follows [Semantic Versioning](https://semver.org/). New releases (major or minor) happen on a "when it's done" basis, while hotfix releases may be released as often as weekly (if necessary). Minor and patch releases should never contain breaking changes. Changes strive to respect the time and effort of site maintainers, extension authors, and so on downstream but are not obligated to maintain compatibility with these modifications.

### Support Policy

Security and critical bugfixes are provided for the current stable release for its lifetime (until the next stable release). Non-critical bugfixes are deferred to the next upcoming release.

Site maintainers are always recommended to upgrade to at least the latest stable release.

## Lorekeeper v3.0

Version 3.0 of Lorekeeper brings many new features and improvements spanning the whole of the project. It also brings significant changes intended to make Lorekeeper easier both to maintain and extend going forward. While there are a few highlights listed here-- as well as some potential areas of caution for those looking to upgrade-- truly, the highlight of this release is the many, many smaller changes that add additional settings or features for functionality in Lorekeeper, make quality-of-life tweaks, and generally help make the project shine.

For a full list of changes, including bugfixes, see [here](version-history/v3.0.md). For upgrade instructions, see the [Upgrade Guide](guides/upgrade.md).

### Updated PHP Requirements

Lorekeeper v3.x requires a minimum PHP version of 8.1, and supports up to 8.3 (in line with Laravel 10). Use of PHP 8.1 was previously recommended as of v2.1 due to drops in PHP 7.4 support, but is now **required**.

Additionally, imagemagick and the `imagick` PHP extension are now required. This is used to process large images more memory-efficiently, addressing out-of-memory issues on some server configurations.

### Update to Laravel 10

This update includes updating [Laravel](https://laravel.com/), the framework underlying Lorekeeper, to Laravel 10 (from 8). While the impact of this is relatively limited, it has some minor impacts in what methods are used for some tasks. This largely impacts extensions, which may need to be updated to account for these changes.

### User Account Updates

#### Authentication Updates

Lorekeeper's authentication system has been updated to use [Laravel Fortify](https://laravel.com/docs/10.x/fortify) under the hood. This enabled the addition of two-factor authentication, which is now available by default for Lorekeeper accounts.

Additionally, several anti-spam measures have been introduced, such as honeypots for login and registration. Additionally, the option to enable Google's [ReCaptcha](https://developers.google.com/recaptcha/) v3 has been added.

#### Deactivation

*This feature originated as the [Deactivate Account](https://wiki.lorekeeper.me/index.php?title=Extensions:Deactivate_Account) extension by [Preimpression](https://github.com/preimpression).*

Users may now deactivate their account if so desired. This serves as a way to remove user data from the public view while avoiding the technical issues inherent to deleting it. This process is non-destructive and reversible, and hides a user's profile and the data attached (except to permissioned staff). Staff may also reactivate user accounts.

#### Registration and Login via Other Platforms

*This feature originated as the [Alias Logins](http://wiki.lorekeeper.me/index.php?title=Extensions:Alias_Logins) extension by [Moif](https://github.com/AW0005).*

Users may now, if enabled, register and login via many of the social media platform(s) supported for aliases. This is configurable and optional.

#### Optional Aliases

Alternately, the alias system may now be made entirely optional if desired. Note that this does not disable the alias system entirely, and it is still recommended to set up one or more of the available options for aliases-- especially if wanting to make use of features that require it, such as automatically assigning ownership of characters associated with an off-site account when it is linked.

### Submission Drafts

*This feature originated as the [Submission Drafts](http://wiki.lorekeeper.me/index.php?title=Extensions:Submission_Drafts) extension by [Preimpression](https://github.com/preimpression).*

Prompt and claim submissions now have a draft state, much like design updates. This allows for users to draft submissions before submitting, and for staff to return submissions in the queue to draft state-- for instance, if changes are needed.

### Optional Rich Text Editor for Comments

Comments now support the "What You See is What You Get" rich text editor in place of the default plain text/markdown comments field. This is optional and must be enabled via the extensions [config file](features/config-files.md).

### Admin Logs and Automatic Rewards for Staff Actions

All staff actions taken by permissioned users are now logged automatically. These logs are only visible to site admins.

Additionally, optional automatic rewards for performing staff actions have been added, building on the above. This feature rewards a configurable quantity of a given currency to permissioned users that perform various staff tasks, such as processing submissions.

### WebP Support

The WebP image format is now supported for image uploads and storage. Included in this change are several additional [config options](features/config-files.md), as well as explicit support for WebP in existing options. These options, if enabled, facilitate storage savings by converting uploaded character and gallery images with minimal loss of image quality.

### Code Maintenance

These changes pertain more to the internal workings of Lorekeeper, but are useful to be aware of if looking to upgrade, update extensions, and so on.

#### Code Formatting

Lorekeeper v3.0 (and on) are subject to automated code formatting. This change isn't visible anywhere except internally, as no functionality has changed as a consequence-- however, enforcing a consistent style ensures that those maintaining and contributing to Lorekeeper know what to expect, and doing so automatically means that it requires no additional effort *to* enforce. While it is liable to complicate the upgrade process due to additional conflicts, especially for heavily modified sites, this is a one-time process.

#### Extension Tracker Updates

Extension tracker entries are now handled as individual files per extension, rather than entries in one large file. This helps prevent disparate entries from conflicting. Extensions from prior to v3.0 will need to update to the new format before being recognized, however.

Additionally, the extension tracker command has received updates; it is now scheduled to run automatically, though will not perform "destructive" operations (such as removing entries for removed extension tracker files) unless manually run.

### Additional Features and Updates

Features marked "Core Extension" are optional features that must be enabled and potentially configured in the extensions [config file](features/config-files.md).

- Various objects around Lorekeeper, such as items, news, and so on now feature convenient edit buttons for staff with the relevant permission(s).
    - *This feature originated as the [Admin Edit Buttons](http://wiki.lorekeeper.me/index.php?title=Extensions:Admin_Edit_Button) extension by [Preimpression](https://github.com/preimpression).*
- Paginated sections with many pages now allow selecting a specific page, even from among "hidden" pages.
    - *This feature originated as the [Pagination Page Selector](http://wiki.lorekeeper.me/index.php?title=Extensions:Pagination_Page_Select) extension by [Speedy](https://github.com/SpeedyD) and [Moif](https://github.com/AW0005).*
- (Core Extension) Sections of the admin sidebar can now be made collapsible.
    - *This feature originated as the [Collapsible Admin Sidebar](https://wiki.lorekeeper.me/index.php?title=Extensions:Collapsible_Admin_Sidebar) extension by [ScuffedNewt](https://github.com/ScuffedNewt).*
- (Core Extension) A "scroll to top" button can now be added to all pages.

#### Characters

- Watermarks can now be automatically resized to a configured percentage of the image size when applied to character images and/or thumbnails.
    - *This feature originated as the [90 Percent Watermark](https://wiki.lorekeeper.me/index.php?title=Extensions:90_Percent_Watermark) extension by [Speedy](https://github.com/SpeedyD).*
- Additional methods have been added for "mentioning" characters-- by name or via thumbnail-- in the rich text editor and/or comments. These are displayed in a new "Mention" tab on character pages.
    - *This feature originated as the [Extended Mentions](https://wiki.lorekeeper.me/index.php?title=Extensions:Extended_Mentions) extension by [Speedy](https://github.com/SpeedyD).*
- Added a command to retroactively watermark existing character images.
- Added the ability to include the year in character codes.
- Added a [config option](features/config-files.md) to disable user uploads of custom thumbnails when masterlist image automation is enabled.
- Added an icon to the character header that copies the character's slug when clicked.
- Added a visibility setting for character categories.
- Added additional [config options](features/config-files.md) and functionality to character image processing.
- The full-size versions of character images, if stored, may now be different image format(s) than the display or watermarked images.
- Character select now autocompletes character codes.
- Design update images now open in a lightbox rather than new tab.
- Prevented design update images from being cached despite file changes.
- (Core Extension) Characters can now have "previous" and "next" buttons, allowing for easy browsing of the Masterlist.
    - *This feature originated as the [Character Prev and Next](http://wiki.lorekeeper.me/index.php?title=Extensions:Character_Prev_and_Next) extension by [Speedy](https://github.com/SpeedyD).*
- (Core Extension) There is now the option, when approving MYO submissions, to either delete or hide the MYO "placeholder" image.
    - *This feature originated as the [MYO Image Removal](http://wiki.lorekeeper.me/index.php?title=Extensions:MYO_Image_Removal) extension by [itinerare](https://github.com/itinerare).*
- (Core Extension) When creating a new image for an existing character, the traits list may be automatically populated from the character's current active image.
    - *This feature originated as the [Auto-populate New Image Traits](http://wiki.lorekeeper.me/index.php?title=Extensions:Autopopulate_New_Image_Traits) extension by [itinerare](https://github.com/itinerare).*

#### Species, Rarities, and Traits

- Added visibility settings for traits, trait categories, species, and subtypes.
- Added the ability to search and sort traits by subtype.
- Added a search filter for uncategorized traits.
- (Core Extension) Trait dropdowns can now be grouped by trait category.
    - *This feature originated as the [Organized Trait Dropdown](https://wiki.lorekeeper.me/index.php?title=Extensions:Organised_Traits_Dropdown) extension by [Draginraptor](https://github.com/Draginraptor).*
- (Core Extension) Added optional trait information modals to the visual trait index.
    - *This feature originated as the [Visual Trait Indexes Trait Modals](http://wiki.lorekeeper.me/index.php?title=Extensions:VTI_Trait_Modals) extension by [Moif](https://github.com/AW0005).*

#### Items and Currencies

- Added an "inventory consolidation" button that condenses like item stacks at user request.
- Added a search filter for uncategorized items.
- Added a visibility setting to item categories.
- Added a "full inventory" page, including items owned by the user's characters.
- Added a summarized view to user and character inventories.

#### Prompts, Submissions, and Galleries

- Added prompt pages/permalinks.
    - *This feature originated as the [Prompt Permalink](https://wiki.lorekeeper.me/index.php?title=Extensions:Prompt_Permalink) extension by [Moif](https://github.com/AW0005).*
- Added the ability to have "staff-only" prompts.
- Added an open/closed search filter for prompts.
- Added a search filter for uncategorized prompts.
- Added several [config options](features/config-files.md) for gallery image processing, including the ability to cap saved image sizes and convert images for storage.
- An "all recent submissions" page has been added to galleries.
    - *This feature originated as the [Gallery Recent Submissions](https://wiki.lorekeeper.me/index.php?title=Extensions:Gallery_Recent_Submissions) extension by [Speedy](https://github.com/SpeedyD).*

#### News and Sales

- Added specific rank powers for news and sales editing.
- Added search and sort options to sales posts.
- Added sidebars to news and sales with recent posts.
- Allow hidden characters to be added to sales posts.
- Sales posts now take the character image at the time a character is added to a sale (rather than the first image).

#### Users and Aliases

- [Discord](guides/socmed/discord.md) has been added as an alias option. It is not supported for alias login at this time.
- Additional methods have been added for "mentioning" users-- by name or via avatar-- in the rich text editor and/or comments. These are displayed in a new "Mention" section on user profiles.
    - *This feature originated as the [Extended Mentions](https://wiki.lorekeeper.me/index.php?title=Extensions:Extended_Mentions) extension by [Speedy](https://github.com/SpeedyD).*
- Added (optional) ability for users to change their own username, with configurable cooldown (in days).
- Added redirect, "previously known as" tooltip if visiting a user's most recent username.
- (Core Extension) [Gravatar](https://gravatar.com) support has been added; users without set avatars may use their Gravatar instead.
    - *This feature originated as the [Gravatar](http://wiki.lorekeeper.me/index.php?title=Extensions:Gravatar) extension by [ScuffedNewt](https://github.com/ScuffedNewt).*
- (Core Extension) Any additional non-primary aliases a user has may now be displayed on their profile. This display is collapsed by default.
    - *This feature originated as the [Aliases on Userpage](https://wiki.lorekeeper.me/index.php?title=Extensions:Aliases_on_Userpage) extension by [Speedy](https://github.com/SpeedyD).*

#### Miscellaneous

- A "maintenance mode" [site setting](features/site-settings.md) and rank power have been added; when enabled, maintenance mode prevents users without the rank power from interacting with the site.
- RSS feeds have been added for news and sales posts.
- Raffles can now have a per-individual ticket cap.
- Added sort options to admin design update, gallery submissions and currency, character transfer, and reports queues.
- Added edit history to comments.
- Added likes, optional dislikes feature to comments.
- Added hashes to "data" images (character categories, currencies, traits and trait categories, items and item categories, prompts and prompt categories, rarities, shops, species, subtypes) to prevent discovery of "hidden" images.
- Prevented Lorekeeper and custom CSS from being cached after file changes.
- Made various styling improvements, including for mobile.
- Various performance improvements have been made.
- A "robots.txt" file has been added to help address excessive crawler traffic.

#### Internal

- Asset retrieval in `loot_select` has moved to the views for better extensibility.
- User profile content has been moved to a separate view to facilitate account deactivation.
- `$dates` properties on models have been removed as of Laravel 10 and replaced with casts. 
- Some queries using `orderByRaw()` have been updated due to incompatibilities with Laravel 10.
- The portions of the `CharacterManager` service pertaining to design updates have been split into their own file, `DesignUpdateManager`.
- Additional admin tables have been converted to bootstrap formatting.
- Composer's lock file is now tracked to facilitate keeping dependencies consistent between development and production environments.
- Various refactors have been made to assist with static code analysis.
- Many other improvements, bugfixes, and other refactors.

Thank you to each and every contributor to Lorekeeper thus far! We couldn't have done it without you.