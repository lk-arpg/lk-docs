# Site Settings

Site settings are editable in the admin panel (requires the **Edit Site Settings** [power](user-ranks.md)).

## Settings

These are the site settings that are added by default during setup.

#### blacklist_key

Optional key to view the blacklist. Enter "0" to not require one.

Default value: 0

!!! info

    This is a password for the blacklist page (if the page is made available for viewing). Note that this is not a very secure method of protecting the blacklist, and is primarily intended for temporary use.

#### blacklist_link

0: No link to the blacklist is displayed anywhere, 1: Link to the blacklist is shown on the user list.

Default value: 1

#### blacklist_privacy

Who can view the blacklist? 0: Admin only, 1: Staff only, 2: Members only, 3: Public.

Default value: 1

#### is_claims_open

0: New claims cannot be made (mods can work on the queue still), 1: Claims are submittable.

Default value: 1

#### is_design_updates_open

0: Characters cannot be submitted for design update approval, 1: Characters can be submitted for design update approval.

Default value: 1

#### is_myos_open

0: MYO slots cannot be submitted for design approval, 1: MYO slots can be submitted for approval.

Default value: 1

#### is_prompts_open

0: New prompt submissions cannot be made (mods can work on the queue still), 1: Prompts are submittable.

Default value: 1

#### is_registration_open

0: Registration closed, 1: Registration open. When registration is closed, invitation keys can still be used to register.

Default value: 1

#### open_transfers_queue

0: Character transfers do not need mod approval, 1: Transfers must be approved by a mod.

Default value: 1

!!! info

    If set to 1, transfers and trades will go through the usual mutual acknowledge/accept process, then get placed into a transfer queue where staff can review the transfer. This also allows staff to edit the transfer cooldown periods of transferred characters.

#### prompt_reward_editing

0: Only mods can edit default prompt rewards for a submission, 1: Users can modify rewards at time of submission.

Default value: 0

#### transfer_cooldown

Number of days to add to the cooldown timer when a character is transferred.

Default value: 3

!!! info

    Note that in circumstances where a staff member has to officiate a transfer, the staff member will still be able to manually edit the cooldown applied in that case (the transfer cooldown is filled in automatically for convenience). This value primarily applies in situations where users transfer characters without requiring approval.

## See Also

- [Config Files](config-files.md)