# Upgrade Guide

!!! example "WIP"

    This is a WIP version of the upgrade guide for Lorekeeper v3.0. Do not use as a reference at this time.

As of v3.0, Lorekeeper requires **PHP 8.1**. No other requirements are changed.

### Summary

- Update your site or server to use PHP 8.1
- Pull the updates, resolving any merge conflicts as appropriate
- Make any config file changes
- (Recommended) Put your site in maintenance mode via `php artisan down`
- Push updates
- Run `composer update` or equivalent and then `php artisan update-lorekeeper-v3`
- (Recommended) Verify that no errors have occurred and use `php artisan up` to remove your site from maintenance mode
- Perform any configuration desired within the site

### Full Guide

Note that this guide assumes hosting on Dreamhost; guides for other hosts will be linked as created by community members. This guide also assumes a basic knowledge of git; see [Tutorial: Introduction To Git](https://wiki.lorekeeper.me/index.php?title=Tutorial:_Introduction_To_Git) if you need to review.

#### Updating your site to PHP 8.1

Note that this assumes your site is currently running PHP 7.4 as recommended for the previous version of Lorekeeper. If you are already running PHP 8.1, you can skip this step. To check, you may consult the Dreamhost control panel and enter `php -v` into PuTTY to check your PHP version.

1. In the Dreamhost control panel, navigate to Domains > Manage Domains via the sidebar
2. Click "Edit" for your site (under "Web Hosting")
3. Under "Web Options", select one of the PHP 8.1 options for "PHP Mode"
4. Click "Change settings". Allow 5-10 minutes or so for changes to process
5. To verify changes, enter `php -v` into PuTTY

If after this php -v returns PHP 7.4 or others, follow these steps in PuTTY to update it (courtesy of[ this guide in the Lorekeeper Discord server](https://discord.com/channels/678909186683437056/763287225839779842/795023074574729216)):

1. Enter `cd ~` to ensure you are in your user directory
2. Enter `nano .bash_profile`. This will open this file in the editor
3. Add `export PATH=/usr/local/php81/bin:$PATH` to the end of the file
4. Save the file by pressing ctrl+x, y, and then enter
5. Enter `. ~/.bash_profile` to update the file you just saved
6. Enter `php -v` again to verify that the update has worked

If this does not resolve the issue, contact support.

#### Pulling Updates

Pull updates from the [Lorekeeper repo](https://github.com/lk-arpg/lorekeeper)'s `main` branch on GitHub. You may have renamed this remote to "origin-old" as part of the set up process.

You may encounter merge conflicts as a result of this. Please see [Tutorial: Installing Extensions - Merging Conflicts](https://wiki.lorekeeper.me/index.php?title=Tutorial:_Installing_Extensions#Merging_Conflicts) for information on how to resolve them. If you did not, or did and have resolved all extant conflicts, commit your changes (if you have not already).

You may wish to make changes to config files now, though you can do so later as well if desired (more information on added configuration options and settings is included later in this guide). If you wish to make changes now, it's recommended you review the following files and change settings as desired:

- `config/lorekeeper/settings`
    - The pre-existing settings file. Additional options have been added in keeping with the addition of extensions from modified-main, etc.
- `config/lorekeeper/extensions`
- `config/lorekeeper/sites`
    - Controls which sites may be used for authentication as well as assisting with link formatting for other sites. Note that any site enabled for auth must also be configured on that platform. See [Social Media Authentication](socmed/index.md) for instructions for supported sites. You may wish to prepare any additional sites you wish to use as an auth option before continuing with the update.

If/when you are ready, commit any changes to config files.

#### Pushing Updates

1. Connect to your site's server via SSH and navigate to your site's `www` directory (`cd ~/site-name.com/www`)
2. **Recommended:** Before pushing any updates to your site, enter `php artisan down` to put your site in maintenance mode. This will prevent any users from making changes while updates are being run, which helps minimize the risk of issues occurring during the update process.
3. Push the changes to your site
4. Enter `composer update` (if you installed composer globally) or `php composer.phar update` (if you installed composer locally only)
5. Enter `php artisan update-lorekeeper-v3`. This will run a variety of commands to update Lorekeeper and any existing data in your site for v3.
6. If you put your site in maintenance mode earlier, enter `php artisan up` to put it back up
7. Verify that no errors have occurred

Your site will now be updated and available to configure as desired.

#### Configuration

Configuration options and settings added as part of this update are listed here for convenience. For additional extension-specific configuration information, consult the extension's documentation.

##### Config Files

All following settings are configured via config files. For more information, see [Config Files](../features/config-files.md).

- `config/lorekeeper/settings.php`
    - `watermark_masterlist_images`
        - Whether or not masterlist images are automatically watermarked.
        - Default: 0
    - `masterlist_image_dimension`
        - Dimension (in px) to scale the shorter dimension (between width/height) of masterlist images to. Set to 0 to disable resizing.
        - Default: 0
    - `masterlist_image_format`
        - Format to convert masterlist images to. Set to null to disable conversion.
        - Default: null
    - `masterlist_image_background`
        - Color (hex code) to fill the background of non-png image types when converting images to file formats that do not support transparency. Set to null to disable. Only takes effect when converting to a file format that isn't png.
        - Default: #ffffff
    - `store_masterlist_fullsizes`
        - Whether to store the full size of masterlist images (relevant if resizing and/or watermarking are enabled). Set to 0 to disable. Not retroactive either way.
        - Default: 0
    - `masterlist_fullsizes_cap`
        - Size (in px) to cap full-sized masterlist images at. Images above this cap in either dimension will be resized, retaining aspect ratio. Set to 0 to disable.
        - Default: 0
    - `watermark_masterlist_thumbnails`
        - Whether or not to watermark masterlist thumbnails. Expects the whole of the character to be visible, so it is recommended to use the thumbnail behavior/disable this if that isn't standard for your site. Set to 0 to disable.
        - Default: 0
    - `masterlist_image_automation`
        - When enabled, replaces the thumbnail cropper and automatically makes all masterlist images square, adding transparent space to the shorter dimension of the image to do so. Thumbnails are consequently resized versions of the full masterlist image.
        - Default: 0
    - `default_purchase_limit`
        - An arbitrary upper limit on the number of an item a user can purchase in a single shop transaction.
        - Default: 99
    - `currency_symbol`
        - Symbol for the (real world) currency used for sales posts.
        - Default: $
- `config/lorekeeper/extensions.php`
    - `navbar_news_notif`
        - Enables [Navbar News Notif](https://wiki.lorekeeper.me/index.php?title=Extensions:Navbar_News_Notif).
        - Default: 0
    - `species_trait_index`
        - Enables [Species Trait Index](https://wiki.lorekeeper.me/index.php?title=Extensions:Species_Trait_Index).
        - Default: 0
    - `character_status_badges`
        - Enables [Character Status Badges](https://wiki.lorekeeper.me/index.php?title=Extensions:Character_Status_Badges).
        - Default: 0
    - `character_TH_profile_link`
        - Enables [Character TH Profile Link](https://wiki.lorekeeper.me/index.php?title=Extensions:Character_TH_Profile_Link)
        - Default: 0
    - `item_entry_expansion`
        - Enables various features of [Item Entry Expansion](https://wiki.lorekeeper.me/index.php?title=Extensions:Item_Entry_Expansion)
        - `extra_fields`
            - Enables extra fields.
            - Default: 0
        - `resale_function`
            - Enables the resale function.
            - Default: 0
        - `loot_tables`
            - `enable`
                - Adds the ability to use either rarity criteria for items or item categories with rarity criteria in loot tables. Note that disabling this does not apply retroactively.
                - Default: 0
            - `alternate_filtering`
                - By default this feature uses more broadly compatible methods to filter by rarity. If you are on Dreamhost/know your DB software can handle searching in JSON, it's recommended to set this to 1 instead.
                - Default: 0
    - `traits_by_category`
        - Enables grouping traits as listed on character pages by category.
        - Default: 0
    - `character_reward_expansion`
        - `expanded`
            - Enables expanded character rewards, allowing items and loot tables to be awarded to characters.
            - Default: 1
        - `default_recipient`
            - Recipient for items that cannot be held by characters. 0 to default to the character's owner (if a user), 1 to default to the submission user.
            - Default: 0
- `config/lorekeeper/sites.php`
    - All sites have the following settings:
        - `full_name`
            - The full name of the site.
        - `display_name`
            - The shortened display name used, for instance, for link formatting.
        - `regex`
            - Regex pattern used to match URLs for the site.
        - `link`
            - The site's URL.
    - Sites which may be used for auth also have these settings:
        - `icon`
            - The Font Awesome icon used to represent the site within the Lorekeeper UI.
        - `auth`
            - Whether or not the site may be used for auth. At least one site must be enabled.
            - Default: 1 for deviantArt, 0 for others
        - `primary_alias`
            - Whether or not aliases from this site may be used as a user's primary alias. At least one site must be enabled.
            - Default: 1 for deviantArt, 0 for others

##### Site Settings

All following settings are configured in the Site Settings admin panel. For more information, see [Site Settings](../features/site-settings.md).

- `admin_user`
    - By default, this is used to direct notifications for comments on site pages to an account. Extensions may also use this setting. It's recommended that this correspond to the ID of an account that is not used by any one person and is solely for administrative purposes.
    - Default: 1
- (Design Update Voting) `design_votes_needed`
    - The number of votes needed for consensus on a design update.
    - Default: 3
- (Galleries) `gallery_submissions_open`
    - Whether or not gallery submissions are open globally.
    - Default: 1
- (Galleries) `gallery_submissions_require_approval`
    - Whether or not gallery submissions require approval.
    - Default: 1
- (Galleries) `gallery_submissions_reward_currency`
    - Whether or not gallery submissions reward currency.
    - Default: 0
- (Galleries) `group_currency`
    - ID of the group currency used for gallery submission rewards, if enabled.
    - Default: 1
- (Reports) `is_reports_open`
    - Whether or not reports are open.
    - Default: 1

##### Site Pages

The content of the following pages is configured via the Pages admin panel. For more information, see [Site Pages](../features/site-pages.md).

- **Credits**
    - Part of/integrated into the larger credits page, which also displays extensions installed on the site. It is supplied via a site page for convenient editing, but does not need to/should not be displayed independently.