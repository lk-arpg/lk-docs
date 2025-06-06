# Release Notes

!!! example "WIP"

    This is a WIP version of the release notes for Lorekeeper v3.0. Do not use as a reference at this time.

## Versioning Scheme

Lorekeeper follows [Semantic Versioning](https://semver.org/). New releases (major or minor) happen on a "when it's done" basis, while hotfix releases may be released as often as weekly (if necessary). Minor and patch releases should never contain breaking changes. Changes strive to respect the time and effort of site maintainers, extension authors, and so on downstream but are not obligated to maintain compatibility with these modifications.

### Support Policy

Security and critical bugfixes are provided for the current stable release for its lifetime. Non-critical bugfixes are deferred to the upcoming release.

Site maintainers are always recommended to upgrade to at least the latest stable release.

## Lorekeeper v3.0

!!! example "WIP"

    Release notes and information on what is included in v3.0 will go here, separate from upgrade instructions.

Version 3.0 of Lorekeeper brings several new features and improvements...

### PHP 8.1

Lorekeeper v3.x requires a minimum PHP version of 8.1, and supports up to 8.3 (in line with Laravel 10). Use of PHP 8.1 was previously recommended as of v2.1 due to drops in PHP 7.4 support, but is now **required**.

### Update to Laravel 10

This update includes updating [Laravel](https://laravel.com/), the framework underlying Lorekeeper, to Laravel 10 (from 8). While the impact of this is relatively limited, it has some minor impacts in what methods are used for some tasks. This largely impacts extensions, which may need to be updated to account for these changes.