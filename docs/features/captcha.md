# Captcha

To combat account creation spam, site owners can enable reCAPTCHA integration through editing the `.env` file. Doing so adds a captcha to the registration page.

## Usage

To enable captchas, add the following to the `.env` file.

```env
RECAPTCHAV3_SITEKEY=sitekey
RECAPTCHAV3_SECRET=secret
```

Site key and secret can be obtained through [here](https://www.google.com/recaptcha/admin/create). Select v3 as the captcha type.

## See Also

- [Invitation Keys](invitation-keys.md)
- [Configuring Lorekeeper](../guides/configuring.md)