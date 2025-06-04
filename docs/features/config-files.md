# Config Files

The configuration files are files in the site’s code that allow customisation of certain features that are highly unlikely to be changed on a regular basis.

## Usage

These files are located in `config/lorekeeper`. The `settings.php` file is the only file that may require any editing at all; the others should not be touched except when coding new features.

## Files

### settings.php

This file lists some basic site settings that are unlikely to change once the site is in use, and therefore should be modified before all else. The following properties can be modified here:

- Site Name
- Character Codes (formatting)
- Masterlist Thumbnail Dimensions
- Trade Asset Limit

Please refer to the comments in the file itself for a complete description of each setting.

### extensions.php

This file lists settings to enable and disable as well as configure certain opt-in extensions integrated into Lorekeeper.

### sites.php

This file lists various sites and values for them and is used to enable/disable available authentication options as well as assist with formatting.

### group_currency_form.php

This file lists form fields and information for inclusion in the group currency form. For more information, see [Galleries](galleries.md).

### extension_tracker.php

This file lists extensions installed on an individual Lorekeeper site and is used to supply information for the `php artisan update-extension-tracker` command. It should only be modified by extension authors.

### admin_sidebar.php

This file lists the links in the admin panel sidebar, as well as the staff power required to view the category of links.

### image_files.php

This file lists the files that will appear in the image uploader section of the admin panel.

### item_tags.php

This file lists item tags that are available to attach to items. Please refer to [the tutorial](../guides/creating-item-types.md) for how to use this file.

### notifications.php

This file lists notification types as well as their message texts.

### powers.php

This file lists staff powers that can be attached to user ranks.

### text_pages.php

This file lists text pages that are generated during setup and cannot be deleted from the admin panel.

## See Also

- [Site Settings](site-settings.md)