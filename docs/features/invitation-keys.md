# Invitation Keys

Invitation keys, used for registering for the site, can be generated in the admin panel (requires the **Manage Users** [power](user-ranks.md)).

## Effects

Invitation keys are only useful when the `is_registration_open` [site setting](site-settings.md) is set to 0. In this case, the registration form will display an additional, required invitation key field and new users will not be able to create an account without a valid key.

## Editing

Keys can be generated in the Invitation Keys section of the admin panel. When generated, a random string will be generated as an invitation code, which can be given to a new user to register an account with. After the user has used the code, their account name will be listed in the table, as well as the date of usage.

Codes that have not been used can be deleted, rendering them unusable.