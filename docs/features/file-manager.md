# File Manager

The File Manager is a feature in the admin panel that can be used to upload files through the site interface. It provides a simple way to upload images that can be used in the descriptions of encyclopedia entries, news posts, etc. as well as other files that may be useful to players of the ARPG, such as drawing bases/PSDs. The File Manager can be used by users with the **Edit Site Settings** [power](user-ranks.md).

## Usage

The File Manager is a simple file uploader for creating folders and uploading files. Folders and files are uploaded to the public/files folder. Using any other method to place/edit files in this folder (e.g. through FTP) will also cause the changes to be reflected in the manager.

Folders can be created up to 1 level deep (no nested folders). Each folder can hold an unlimited number of files (only limited by amount of storage space your webhosting plan provides). Folders can be renamed and deleted, both of which will break existing links to any of their contents.

Files can be uploaded one-by-one to the base folder and any created folders. There is no restriction on the file type. The file size is limited by the maximum upload size as specified in your server's php.ini, and may or may not be an accurate representation of the maximum size of file you can upload - the displayed maximum size is a guideline, and avoiding uploading excessively large files is recommended.

Files in a folder are listed in the folder page. The files can be accessed by clicking on the file names. Files can be moved, renamed or deleted, which will break existing links to any of them.

## Editing

Folders have the following properties:

- Name

**Name** is the folder's name. This should be unique (not the name of an existing folder), and use only alphanumeric characters and dashes/underscores only.

File uploads present only an upload. The move form allows the user to select a destination folder, and will overwrite any existing file in the destination folder with the same file name. Similarly, the rename feature will also overwrite an existing file with the same name. It can also be used to change the file extension of the file, but this may cause unintended behaviour and thus is not recommended.

## See Also

- [Site Settings](site-settings.md)
- [Site Pages](site-pages.md)