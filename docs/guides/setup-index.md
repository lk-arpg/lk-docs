# Getting Started

!!! example "WIP"

    This guide-to-guides is a proposed WIP for a new overarching setup guide structure. This structure is focused on making setup information more modular, so that individual parts can be mixed and matched without need to reference across guides. It also focuses on incorporating previously community-maintained guides into the documentation itself, so that these guides are more easily maintained going into the future. Feedback on and improvements to it, as well as contributions to the individual guides, are much appreciated!

    Consequently, this may or may not be useful as a guide until more finished. Please refer to existing community set-up guides until further notice!

There are several components to Lorekeeper setup, so installation information is broken into several parts. This page aims to give a general overview of the steps required and link to guides for each part of the process.

The information here makes an effort to assume no technical background on the part of the reader. Consequently, some of the steps in this index recommend action for readers with existing technical background, depending on the nature thereof. If the latter applies to you, it's recommended you read the [developer introduction](dev-intro.md), as Lorekeeper and its ecosystem are somewhat unusual.

## Local Set-up

This section concerns setting up the tools-- software-- that you will need to work with Lorekeeper, and obtaining a copy of the code. As the recommended tools depend heavily on which platform (or operating system) you are working on, information is provided for several platforms.

Topics covered:

- Working with git, setting up a graphical git client
- Setting up to connect to a remote server using SSH

!!! example "WIP"

    Currently, these links all lead to different sections of one page, under the assumption that the whole page will not end up too long (as it should only cover basic setup of tools). This may or may not end up being correct.

Local setup on:

- [Windows](local-setup.md#windows)
- [Mac](local-setup.md#mac)
- [Linux](local-setup.md#linux)

If you are already familiar with these subjects and have a preferred workflow, clone `https://github.com/lk-arpg/lorekeeper.git` via your preferred method and move on to the next step.

### Setting up a Local Development Environment

Before moving ahead to setting up a live Lorekeeper site, it's recommended to set up a local or development environment so that you can preview and test your changes as you make them-- and *before* pushing them to a live site. This helps catch errors (especially large or breaking ones!) before they become larger problems, and is especially key if you plan to (or have already) modified your Lorekeeper site heavily!

It also provides a testing-ground to experiment or become more familiar with Lorekeeper at no cost, as it does not require a domain name or hosting.

As above, this process is heavily dependent on your local platform, and is broken up into several guides.

Topics covered:

- Setting up PHP, MySQL (or MariaDB), and a webserver on your local machine
- Installing composer locally
- Serving your local files and working with them locally

!!! example "WIP"

    As development environment setup is liable to be more involved than basic setup of tools-- and may offer multiple options, e.g. for serving site files locally on Windows-- these currently link to separate pages.

Development environment setup on:

- [Windows](dev-setup-win.md)
- [Mac](dev-setup-mac.md)
- [Linux](dev-setup-linux.md)

If you already have a preferred workflow for developing PHP-based applications, do so for the local files you set up in the previous step and move on to the next one.

## Webserver Set-up

This section concerns setting up a webserver to host your Lorekeeper site so that it is accessible via the internet at large. The steps involved here are generally *host* rather than platform-specific, as in most cases you will be working with some form of Linux server.

!!! example "WIP"

    Some of these are highly theoretical/not subjects we've covered previously. However, as they come up often and are likely to be useful to those with a non-technical background coming to Lorekeeper, they feel worth covering.

Topics covered:

- Obtaining a domain name
- Selecting hosting
- Setting up on a given host

!!! example "WIP"

    Both the DigitalOcean and Hetzner guides are ultimately going to boil down to a "bare-bones VPS setup" guide, so it's likely worth writing that as its own guide and linking to it from them.

Setting up a site on:

- [Dreamhost](hosts/dreamhost.md)
- [DigitalOcean](hosts/digitalocean.md)
- [Hetzner](hosts/hetzner.md)
- [Linux Server (General)](hosts/linux.md)

Even if familiar with publishing Laravel-based sites, it's recommended to review the instructions before doing so and moving on to the next step.

## Configuring Lorekeeper

This section concerns configuring Lorekeeper itself. It also covers the process of obtaining various API keys needed for connected services, such as to handle mail, user verification, and so on.

!!! example "WIP"

    Obtaining API keys and setting up .env are technically later here than the previous setup guide, but as these are universally necessary, they feel better suited to this step than the previous.

Topics covered:

- Obtaining necessary API keys
- Setting up an `.env` file
- Configuring Lorekeeper via [config files](../features/config-files.md)
- Configuring Lorekeeper via [site settings](../features/site-settings.md)

See [Configuring Lorekeeper](configuring.md).

Once complete, you should have a live Lorekeeper site, configured to your liking!