# Configuring Lorekeeper

!!! example "WIP"

    This is a WIP guide to configuring Lorekeeper, and should not be used as a reference in its current state.

## Setting up an .env file

In order for your site to become operational, you will need to provide various pieces of sensitive information. This information **should never be committed via git**, and is dependent on environment (local vs live), so it is handled via a separate file, `.env`, placed in the root directory of your site (in the `www` directory).

!!! example "WIP"

    The example .env probably needs updating; this is mostly copied from the old setup guide.

This can be done by navigating to the `www` directory and running `nano .env`; this will open an empty file in the editor. Paste in the following, filling out the fields as noted (avoid using spaces in names):

```
APP_NAME=site_name_with_no_spaces
APP_ENV=
APP_KEY=
APP_DEBUG=
APP_URL=

CONTACT_ADDRESS=your_contact_address@site-name.com
DEVIANTART_ACCOUNT=your-dA-group-account-username

LOG_CHANNEL=stack

DB_CONNECTION=mysql
DB_HOST=
DB_PORT=
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=

BROADCAST_DRIVER=log
CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=
MAIL_HOST=
MAIL_PORT=
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_FROM_ADDRESS=noreply@site-name.com
MAIL_FROM_NAME=mail_sender_name

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_APP_CLUSTER=mt1

MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

DEVIANTART_CLIENT_ID=your_deviantart_client_id
DEVIANTART_CLIENT_SECRET=your_deviantart_secret
DEVIANTART_CALLBACK_URL=/
```

Leave the APP_KEY blank, as it will be generated in a later step.

### Initializing your Site

On both local and on the server, run the following, letting each complete before the next one:

```sh
php artisan key:generate 
php artisan migrate
```

This will generate the app key (used for encryption) and create Lorekeeper's database tables.

Run the following commands afterwards:

```sh
php artisan add-site-settings
php artisan add-text-pages
php artisan copy-default-images
```

Next, set up the admin user:

```sh
php artisan setup-admin-user
```

This will prompt you for the creation of the admin account, which will have access to all site data. On the live site, it is **highly recommended** to use this as a purely administrative account, i.e. separate from any personal account(s) used by administrator(s). You can run this command again to change the email address and password of the account.

At this point, you should be able to log into the site with the admin account.

### Setting up the Scheduler

Run the following to edit your crontab file:

```sh
crontab -e
```

Add the following line, editing the directory name as necessary:

```sh
* * * * * cd ~/site-name.com/www && php artisan schedule:run >> /dev/null 2>&1
```

### Connecting to Other Services

#### Mail

You will need to connect to a service that will allow your site to send emails; this is used on registration (to verify the email address a user provides) and in the event that a user forgets their password. Lorekeeper does not provide support for sending any other mail out-of-the-box.

!!! example "WIP"

    Contributions welcome-- please add guides to the guides/mail directory and link them here, one per service!

There are several services that can provide this capability:

- List
- Services
- Here

#### Authentication

By default, Lorekeeper expects users to connect at least one off-site account to their on-site account for the purposes of verification, log-in (optional), and/or display.

Note that these instructions only include specific instructions for each platform as necessary, and do not include universal steps such as configuration.

The available platforms are:

- [deviantArt](socmed/deviantart.md)
- [Discord](socmed/discord.md)
- [Imgur](socmed/imgur.md)
- [Instagram](socmed/instagram.md)
- [Toyhou.se](socmed/toyhouse.md)
- [Tumblr](socmed/tumblr.md)
- [Twitch](socmed/twitch.md)
- [Twitter](socmed/twitter.md)

## Changing Config Files

In your local copy, open up the config file(s) in your text editor of choice. The code is commented in detail, so you can read and modify the settings as you need.

Some config files you may want to edit:

- `config/app.php`
    - Most settings do not need to be touched since you wrote them in .env, but you may want to edit the **timezone** to match the clock your community goes by.
- `config/lorekeeper/settings.php`
- `config/lorekeeper/extensions.php`
- `config/lorekeeper/sites.php`

For more information, see [Config Files](../features/config-files.md).

In your Git client, choose the modified files, commit and push them (important: to your server, not Github!) with a helpful message. If the hooks have been set up correctly, you should see the effects on the live site after it's done. If not, and there were no errors, you may need to run `php artisan config:clear` on the server.

## Changing Site Settings

Now you can start editing the site data. All changes on the live site will only stay on the live site, and all local changes will only remain local.

Log in as the admin user and go to the admin panel (click the crown in the navigation bar). The first things you may want to edit are:

- [Site Settings](../features/site-settings.md)
- [User Ranks](../features/user-ranks.md) (create moderator ranks)
- [Pages](../features/site-pages.md) (Terms of Service, Privacy Policy, About)
- [Site Images](../features/site-images.md)

## Setting up Site Data

You may want to edit in order:

- [Rarities](../features/rarities.md)
- Categories (trait categories, item categories, prompt categories, [character](../features/characters.md) categories)
- [Species](../features/species.md), [Traits](../features/traits.md), [Items](../features/items.md), [Currencies](../features/currencies.md)
- [Loot tables](../features/loot-tables.md)
- [Galleries](../features/galleries.md), [Prompts](../features/prompts.md), [Shops](../features/shops.md)

Note that at least one character category is required to create any characters.

More specific information about each type of data can be found on the respective documentation pages.