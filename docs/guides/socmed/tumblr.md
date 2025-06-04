# Authentication with Tumblr

## Registering your Application

Tumblr application creation can be accessed at [https://www.tumblr.com/oauth/register](https://www.tumblr.com/oauth/register).

- **Application Name:** Provide a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
- **Application Website:** Enter your site's address, for instance `https://lorekeeper.me`
    - For local testing, use `http://localhost/`
- **Application Description:** Enter a brief description of your app.
    - For example: "Authenticates a Lorekeeper user with their Tumblr account."
- **Administrative contact email:** Enter your email address.
- **Default callback URL:** `https://your-site.com/auth/callback/tumblr`

## Connecting to Lorekeeper

The Tumblr application portal can be accessed at [https://www.tumblr.com/oauth/apps](https://www.tumblr.com/oauth/apps).

You can access the client ID and client secret from this page.

In your .env file, add the lines:

```
TUMBLR_CLIENT_ID=your_client_id_here
TUMBLR_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.