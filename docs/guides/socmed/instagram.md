# Authentication with Instagram

!!! warning "The instructions on this page are currently incomplete."

    Please see the content of the page for reasons why. If you believe you can help, please submit a [pull request](https://github.com/lk-arpg/lk-docs/pulls).

Instagram is by nature connected to Facebook and as such requires a Facebook developer account.

## Developer Sign-up

Facebook developer signup can be accessed at [https://developers.facebook.com/async/registration/](https://developers.facebook.com/async/registration/).

After signing up you can create an app immediately.

## Registering your Application

The Facebook application portal can be accessed at [https://developers.facebook.com/apps/](https://developers.facebook.com/apps/).

Please note that Facebook loads captchas in iframes. You may need to disable ad blocking for the captcha to appear.

1. Click on "Create App".
    1. Select "Build Connected Experiences".
    2. In your app display name, enter a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
    3. Fill remaining forms as appropriate.
    4. Once your app is created, you will be taken to your app dashboard.
2. In the sidebar, click on Settings, then Basic.
3. Scroll to the bottom of this page and click "**+ Add Platform**".
    1. Choose "Website".
    2. In the field, add your site URL.
        - For local testing, use `http://localhost/`
4. Click on Dashboard, and scroll down to "**Add Products to Your App**".
5. Click on the "Set Up" button for "**Instagram Basic Display**".
6. Click on "Create New App" at the bottom of the page.
    - For the **Display Name**, use the simple but descriptive title you used for your Facebook app.
    - Fill in the **redirect URI:** `https://your-site.com/auth/callback/instagram`

You will now be able to retrieve your client ID and client secret. You will need to enter your password to view the client secret.

### App Review

This section is incomplete pending testing and more thorough documentation.

In order for all users to be able to authenticate, you must submit your application for review; otherwise, only "test users" will be able to authenticate with your app. Submitting your application for review requires providing additional information about your app. It also requires the ability to delete data/deauthorize user accounts on request which are not as of yet built-in features of Lorekeeper. It may as of yet be possible as the only data stored within Lorekeeper is the user's username, however, which unlinking the social media account removes. In conclusion: this may be manageable, however, we have an inadequate understanding of the app review process and how to best negotiate it with regards to Lorekeeper due to the difficult nature of testing such a thing.

You can read about adding test users here: [https://developers.facebook.com/docs/instagram-basic-display-api/getting-started#step-3--add-an-instagram-test-user](https://developers.facebook.com/docs/instagram-basic-display-api/getting-started#step-3--add-an-instagram-test-user)

## Connecting to Lorekeeper

In your .env file, add the lines:

```
INSTAGRAM_CLIENT_ID=your_client_id_here
INSTAGRAM_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.