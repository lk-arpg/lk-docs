# Prompts

Prompts are a submission type that accepts user submissions into a queue and distributes rewards when approved. They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md). See [Claims](claims.md) for collecting rewards that do not have a prompt specified.

## Usage

!!! info "This section pertains to the general purpose and usage of the prompt index page. See the [Submission](#submission) section below for more information on submitting prompts."

Prompts can be accessed from the navigation bar, under the World dropdown. The prompt index lists all visible prompts, sorted by category order, and can be further filtered by the following:

- Name
- Category

Additionally, prompts can be sorted by:

- Name (alphabetical order)
- Category
- Newest First (creation date)
- Oldest First
- Starts Earliest
- Starts Latest
- Ends Earliest
- Ends Latest

Each prompt lists the following:

- Name
- Start date (if applicable)
- End date (if applicable)
- Summary
- Details (collapsed)
    - This also notes if submissions to the prompt are temporarily or indefinitely hidden
- Rewards
- Button for submission (if allowed)

Prompts can only be submitted between the start and end dates if either or both of those dates are specified. Clicking the Submit Prompt button goes to the prompt submission page with the prompt already selected.

## Editing

!!! info "This section pertains to the editing of prompt categories and prompts. See the [Approval Queue](#approval-queue) section below for more information on the approval queue."

### Categories

Editing prompt categories and prompts requires the **Edit World Data** power. Note that this power alone does not allow the user to view and process the submission queue.

Prompt categories can be created in the admin panel, with the usual category properties:

- Name
- World Page Image
- Description (accepts HTML)

The image and description are displayed only on the world page. Besides being used to organise prompts on the prompt submission page, submissions in the approval queue can also be filtered by category, which can be used to help distribute moderation work.

### Prompts

Prompts themselves have the following properties:

- Name
- Prompt Category
- Summary (no HTML)
- Description (accepts HTML)
- Start Time
- End Time
- Hide Before Start Time
- Hide After End Time
- Is Active
- Hide Submissions

**Name** is the prompt name which is displayed on the prompt index.

**Prompt Category** is the category to which the prompt falls under, and used for organisation.

**Summary** is a short blurb about the prompt that is immediately visible on the prompt index. This is intended to be just a concise one-liner that gives users a rough idea of what the prompt is about.

**Description** is a longer description about the prompt. Details and specifications about the prompt requirements can be described in greater detail here. It accepts HTML, so you can insert images.

**Start Time** and **End Time** note the period during which the prompt can be submitted. Both are optional, and you can also specify only one of them.

**Hide Before Start Time** and **Hide After End Time** additionally prevent the prompt from showing on the index when it cannot be submitted to. This is useful, for example, if you would like to keep event prompts secret until the event is live.

**Is Active** toggles the visibility of the prompt altogether. This overrides the hiding options - if this is set to not active, the prompt will never show on the index.

**Hide Submissions** controls whether or not submissions to a prompt should be hidden until the prompt's end (if an end date is set) or indefinitely. Staff with the **Manage Submissions** power will be able to see all submissions regardless of this setting.

#### Rewards

The rewards section allows you to attach some default rewards to the prompt. Users will not be able to edit these rewards during submission.

You can attach any of the following, specifying a quantity:

- Item
- Currency
- Loot table
- Raffle Ticket

Note that loot table quantity rolls the table x times, and not the rewards from 1 roll multiplied by x. Only the display name of the loot table will be shown - users will not see the internal name of the table, nor the contents/odds of rolling.

These rewards are not permanent and can be edited during approval time.

## Submission

Responses to prompts can be submitted from the prompt submission page. A quick link is also available from the submit dropdown on the right hand side of the nav bar.

A prompt submission requires:

- Prompt
- Submission URL
- Comments (no HTML; accepts line breaks)
- Rewards

**Prompt** is the prompt that is being responded to. If the submit button on the prompts page is clicked, this field will already have been filled.

**Submission URL** is the link to a page containing the material to be reviewed for prompt submission. This is expected to be something like a [gallery](galleries.md) submission, but can be anything relevant.

**Comments** are optional. This space could be used for, for example, entering calculations for tiered rewards. Line breaks will be preserved, but HTML will not be rendered.

### Rewards

The rewards section allows the user to select additional rewards. They can choose to add any of:

- Items
- Currencies

Loot tables cannot be selected. This selection is added on top of the default rewards, which are also displayed below the reward selection area.

### Characters

The characters section allows the user to add characters to their submission. Inputs are:

- Character Code
- Rewards

**Character Code** refers to the character's unique identification code.

**Rewards** function much like the user selected rewards, but only currencies can be selected, and these rewards will be credited directly to the character on approval.

### Expanded Rewards

An optional extension toggleable in the extensions [config file](config-files.md) allows additional reward types to be awarded to characters. These are:

- Items
- Loot Tables

The config file also contains a toggle for how to handle rewards that cannot be held by characters (whether they go to the character's owner or to the submitting user).

### Submission

Submissions submitted to the approval queue cannot be edited by the user. The submission will have its own page containing all submitted information - this will not be visible to any users besides the submitter and users with the Manage Submissions power until it is approved. If the prompt is set to not show submissions until the end of the prompt or indefinitely, it will not become visible to other (non-permissioned) users until the prompt ends or the setting is changed, respectively.

## Approval Queue

Users with the **Manage Submissions** power can view the queue, edit rewards and approve/reject submissions.

The prompt approval queue consists of lists of submissions filtered by status, ordered by newest first. Submissions can be further filtered by prompt category. Pending submissions can be acted upon, while approved and rejected submissions are for reference only.

Clicking the edit button takes the user to the submission review page, where they can edit the rewards attached to the submission.

### Rewards

The user rewards section lists the **combined** default rewards and any additional rewards the user may have selected. Please take care when checking that the rewards are appropriate for the submission, as the user may have added something extra! A list of the default rewards is displayed for reference. The selectable area contains everything the user will receive when their submission is approved.

The character rewards section lists the characters and rewards the user has added that will be given to the selected characters. More characters can be added as well.

### Processing

The submission can be approved or rejected using the buttons at the bottom. Clicking either will notify the user that their submission has been processed.

In the case of approval, any attached rewards will be automatically distributed to the user and characters. The submission page will become publicly visible.

In the case of rejection, a comment can be provided to the user. This can be used to inform the user about why their submission was rejected. HTML cannot be used, and the reason will be displayed on the submission page. The submission page remains hidden to users other than staff with the Manage Submissions power and the submitter themselves.

## Logging

A list of prompt/claim submissions a user has made is linked from their user profile. Similarly, characters also have a page that lists prompts/claims they have been submitted for rewards in.

## See Also

- [Characters](characters.md)
- [Claims](claims.md)