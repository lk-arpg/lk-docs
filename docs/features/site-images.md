# Site Images

Site Images is a feature in the admin panel that is used to replace the images used in the site layout. It also provides an upload for a CSS file that can be used to insert CSS into the site layout without editing the site code directly. This page can be used by users with the E**dit Site Settings** [power](user-ranks.md).

## Usage

The Site Images page provides uploads for the following images:

- Header Image
- Characters Icon
- Account Icon
- Inventory Icon
- Currency Icon
- MYO Default Image
- MYO Default Image (Thumbnail)

**Header Image**: The header banner displayed at the top of the page. PNG format, default height of 200px. Tiles in both directions.

**Characters Icon**: The characters graphic on the front page. PNG format, default size of 200px x 200px (no restriction).

**Account Icon**: The account graphic on the front page. PNG format, default size of 200px x 200px (no restriction).

**Inventory Icon**: The inventory graphic on the front page. PNG format, default size of 200px x 200px (no restriction).

**Currency Icon**: The bank graphic on the front page. PNG format, default size of 200px x 200px (no restriction).

**MYO Default Image**: The default image used for MYO slots when no image is uploaded. PNG format, no size restriction.

**MYO Default Image (Thumbnail)**: The default masterlist thumbnail used for MYO slots when no image is uploaded. PNG format, size of masterlist thumbnails.

Additionally, there is an upload under the heading Site CSS. This file will be included after all other CSS files that are added to the page. Reuploading the file will replace the original.

## Editing

A single upload is presented for each. The "View Current" button can be clicked to visit the URL of the file, though previews of each image are given next to each field.

On the command line, the following command can be run to overwrite uploaded images with the default ones. This command also works to copy default images over when none are present.

```sh
php artisan copy-default-images
```

Maximum image file sizes are subject to as specified in `php.ini` on your server - if your image is failing to upload, it may be too large. (Large images are not recommended either, as this will consume large amounts of bandwidth on each page load.)

## See Also

- [Site Settings](site-settings.md)
- [File Manager](file-manager.md)