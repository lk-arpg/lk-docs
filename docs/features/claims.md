# Claims

Claims are a submission type that accepts user submissions into a queue and distributes rewards when approved. Unlike [Prompts](prompts.md), they do not require the user to choose a prompt for submission.

## Submission

Claims can be submitted from the claim submission page. A quick link is also available from the submit dropdown on the right hand side of the nav bar.

A claim submission requires:

- URL
- Comments (no HTML; accepts line breaks)
- Rewards

**URL** is the link to a page containing the material to be reviewed for claim submission. This is expected to link to proof (e.g. a comment, screenshot etc.) that the user is allowed to make this claim.

**Comments** are optional. This space could be used for, for example, entering a reason/purpose for making the claim. Line breaks will be preserved, but HTML will not be rendered.

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

### Submission

Submissions submitted to the approval queue cannot be edited by the user. The submission will have its own page containing all submitted information - this will not be visible to any users besides the submitter and users with the Manage Submissions power until it is approved.

## Approval Queue

Users with the **Manage Submissions** power can view the queue, edit rewards and approve/reject submissions.

The claim approval queue consists of lists of submissions filtered by status, ordered by newest first. Pending submissions can be acted upon, while approved and rejected submissions are for reference only.

Clicking the edit button takes the user to the submission review page, where they can edit the rewards attached to the submission.

### Rewards

The user rewards section lists the rewards the user has selected. The selectable area contains everything the user will receive when their submission is approved.

The character rewards section lists the characters and rewards the user has added that will be given to the selected characters. More characters can be added as well.

### Processing

The submission can be approved or rejected using the buttons at the bottom. Clicking either will notify the user that their submission has been processed.

In the case of approval, any attached rewards will be automatically distributed to the user and characters. The submission page will become publicly visible.

In the case of rejection, a comment can be provided to the user. This can be used to inform the user about why their submission was rejected. HTML cannot be used, and the reason will be displayed on the submission page. The submission page remains hidden to users other than staff with the Manage Submissions power and the submitter themselves.

## Logging

A list of prompt/claim submissions a user has made is linked from their user profile. Similarly, characters also have a page that lists prompts/claims they have been submitted for rewards in.

## See Also

- [Characters](characters.md)
- [Prompts](prompts.md)