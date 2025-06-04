# Galleries

Galleries are a submission type that accepts user images (typically art) and writing into a queue for inclusion in one of a site's galleries/folders. Galleries can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md).

## Usage

!!! info "This section pertains to the general purpose and usage of the gallery index. See the Submission section below for more information on submitting to a gallery."

The overall gallery can be accessed from the navigation bar. The gallery index lists all visible top-level galleries. These are displayed in the order specified by staff when creating/editing galleries.

Each gallery in the index lists the following:

- Name (with link to the full gallery)
- A list of the gallery's sub-galleries, if present
- The four most recent submissions to the gallery, each including:
    - Thumbnail
    - Title
    - Artist(s)/Author(s)
    - Number of favourites
    - Number of comments

If a gallery contains no submissions, but has sub-galleries which contain them, submissions to the sub-galleries will be shown instead.

### Galleries

Each gallery has a page that displays the following:

- Name
- Open and/or close date, as applicable
- Description
- All submissions to the gallery, paginated, as outlined above
- The submit to gallery button, if a user is logged in

Submissions in a gallery can be searched by title, associated prompt ID (as applicable), and sorted by:

- Newest First (creation date)
- Oldest First
- Title (alphabetical order)
- Title (reverse alphabetical order)
- By prompt (newest to oldest)
- By prompt (oldest to newest)

Pieces can only be submitted to a gallery between the start and end dates if either or both of those dates are specified. Clicking the Submit button goes to the gallery submission page for that gallery.

### User and Character Galleries

Each user and character has their own gallery. For users, this displays all gallery submissions the user has made.

For characters, this is separate from their [images](character-images.md) and displays all submissions that the character is attached to. Character galleries have a disclaimer at the top noting that the images therein are user-generated and not to be confused with the official record of the character as seen in the character's images. In this sense, it is similar to the character's submission log.

### Favourites

Users can add approved gallery submissions to their favourites. This is done by means of a button visible either alongside the gallery submission's thumbnail or on the gallery submission's page. A user's favourites are displayed in a gallery on their profile. There is also an automatically populated gallery of the user's favourites which have characters they currently own attached.

## Editing

!!! info "This section pertains to the editing of galleries. See the Queues section below for more information on the submission queues."

Gallery editing requires the **Edit World Data** power. Note that this power alone does not allow the user to view and process the submission queues.

Galleries have the following properties:

- Name
- Sort
- Parent Gallery
- Description (no HTML)
- Submissions Open
- Enable Currency Rewards
- Prompt Selection
- Votes Required
- Hide Before Start Time
- Start Time
- End Time

**Name** is the gallery name which is displayed on the gallery index and gallery itself.

**Sort**, optional, is a number and does not need to be unique. Galleries are sorted first by their sort number, then by name.

Sub-galleries are also sorted this way, but only displayed within the context of their parent gallery, so a sub-gallery with a sort number of 1 will only ever display at the top of its' parent gallery's list of sub-galleries.

The **Parent Gallery**, optional, is the gallery that the gallery being created/edited falls under, used for organization.

The **Description** field allows for a short description of the gallery. This is shown on the gallery's page.

**Submissions Open** controls whether or not users can submit to the gallery. Users with the Manage Submissions power can submit to any gallery regardless of this setting.

Note that no users may submit regardless of powers if the `gallery_submissions_open` [site setting](site-settings.md) is set to 0.

**Enable Currency Rewards** controls whether submissions to the gallery are eligible for group [currency](currencies.md) rewards. This option only appears if the `gallery_submissions_reward_currency` site setting is enabled.

**Prompt Selection** controls whether or not users will be given the option to select a [prompt](prompts.md) to associate with a gallery submission when submitting to the gallery.

This is primarily useful for galleries which may see submissions intended for multiple different prompts, as it helps keep them organized from the outset.

**Votes Required** is the number of votes required to approve a submission to this gallery in the approval queue. This option only appears if the `gallery_submissions_require_approval` site setting is enabled.

**Hide Before Start Time** prevents the gallery from showing on the index before it can be submitted to. Note that galleries can only be hidden before starting, not after their end.

**Start Time & End Time** note the period during which submissions to the gallery can be made. Both are optional, and you can also specify only one of them.

### Currency Rewards

This optional component, enabled using the `gallery_submissions_reward_currency` site setting, allows submissions to applicable galleries to receive rewards of a set on-site currency. When submitting to a gallery with currency rewards enabled, users will be shown a short form that is used to calculate an estimated currency total that they should receive for the piece. This estimate will be provided to users managing the associated queue, though they can adjust as appropriate. This component *will* work on initial installation but *will **not*** be customized to your site, so it is **highly recommended** that it be configured as appropriate. This has three parts:

- `group_currency` site setting
    - The ID of the currency that is used for rewards.
- **The Form**
    - This part-- displayed to users when creating a gallery submission-- is configured in a [config file](config-files.md) (specifically `config/lorekeeper/group_currency_form.php`). This file is commented extensively in an effort to make it easier to customize.
- **The Function**
    - This part takes input from the form and uses it to calculate an estimated reward that should be given for a gallery submission. It is at the beginning of and configured in `app/Helpers/AssetHelpers` and similarly commented extensively. Note that the fields used in this function must correspond to the form, or it will break and/or fail to calculate the total properly.

## Submission

Submissions to a gallery can be submitted from the gallery index (via the + button on the gallery's listing) or via the "submit" button on the gallery's page.

A gallery submission requires:

- Main Content (An image and/or text (accepts HTML))
- Title
- Description (accepts HTML)
- Content Warning (no HTML)
- Prompt

**Main Content** is the primary content of the gallery submission. This can take the form of an image and/or text (for literature with an accompanying illustration, for example).

**Title** is the title of the gallery submission, shown in the gallery.

**Description** is optional. This space may be used for any comments the submitting user would like to make about the piece.

**Content Warning** is optional. The submitting user may provide a short content warning if deemed appropriate; if so, the submission's thumbnail will be displayed as a generic image (see [Site Images](site-images.md)) and the warning will be displayed below the thumbnail. The piece will still be visible in full when visiting the gallery submission's page.

**Prompt** is optional and only available if enabled for the gallery being submitted to. If available, the prompt the gallery submission is for may be selected. This is useful primarily as an organizational tool, as gallery submissions will automatically find and display prompt submissions using the gallery submission.

### Characters

The characters section allows the user to add [characters](characters.md) to their submission. The only input is the **character code** (the character's unique identification code).

Characters added to a submission are displayed on the submission's page; if currency rewards are enabled for the site and gallery being submitted to, the number of characters attached to the submission is also used to help calculate the estimated reward.

### Collaborators

If a piece is a collaboration between multiple users, the submitting user can specify each user that participated, **including themself**.

Collaborators require the following:

- User
- Role (no HTML)

**User** allows selection of an on-site user.

The **Role** field is for specifying what part(s) of a piece the user contributed.

When submitting a gallery submission with collaborators associated, the collaborators will be [notified](notifications.md) and must approve or edit the record of their contribution before the submission appears in the gallery (if submissions do not require approval) or before it appears in the submission queue for staff approval. Contributors can also remove themself from the submission at this time if they have been added erroneously. Once all collaborators have approved, the submission is processed further.

### Participants

Participants are similar to collaborators, though not directly involved in the creation of the submission.

Participants require the following:

- User
- Role

**User** allows selection of an on-site user.

**Role** allows for selection from one of the following:

- Gift for
- Trade for
- Commissioned by
- Commissioned by (for group currency)

Participants are notified that they have been added to a gallery submission once it is approved.

### Currency Rewards Information

If currency rewards are enabled for the site and gallery being submitted to, the user will be asked to fill out the currency reward form as configured. Once the gallery submission has been submitted, the site will use this information to calculate an estimated amount of currency that the user and/or any collaborators should receive.

### Submission

Gallery submissions submitted to the approval queue or gallery (depending on settings) will have their own page containing submitted information. Submissions are visible to the submitting user and/or all collaborators as well as to users with the Manage Submissions power before approval, and to all users once the submission is accepted into the gallery.

### Editing

Gallery submissions can be edited after submission by the submitting user as well as users with the Manage Submissions power, though some properties cannot be edited either after submission or after approval. The properties that can always be edited are:

- Main Content
- Title
- Description

The properties that can be edited before approval are:

- Collaborators
    - Note that any collaborators added after submission will not receive a notification
- Participants

The properties that cannot be edited after submission are:

- Currency form information (if enabled)
- Selected prompt (if enabled)
    - Users with the Manage Submissions power can always edit this, however.

Additionally, users with the Manage Submissions power can select a different gallery to move an already submitted gallery submission to. This is available regardless of the submission's status. Note that if a submission is moved between galleries that do/do not have currency rewards enabled, the relevant information will not be created/will not be displayed, and the submission will not be added to the rewards queue, depending on the direction of the move.

#### Archiving Submissions

As gallery submissions may hold records important to the logging and recordkeeping of the site-- particularly if currency rewards are enabled-- they cannot be deleted. However, the submitting user, as well as any users with the Manage Submissions power, can "archive" gallery submissions, rendering them non-visible to other users.

### Submission Log Details

Gallery submissions have an additional page that contains non-public details about the submission and information pertinent to queue processing. This page is visible to the submitting user and/or any collaborators as well as users with the Manage Submissions power. This page displays:

- Basic information about the gallery submission
    - Thumbnail
    - Title
    - Gallery
    - Submitting user and/or collaborators
    - Created/updated at
- (If currency rewards are enabled) Currency reward information
    - Responses from the currency form are recorded here
    - Users with Manage Submissions may view the estimated numbers that should be rewarded

## Queues

Users with the Manage Submissions power can view the queue(s), vote on submission approval/rejection, and (if enabled) reward currency for gallery submissions.

Both the approval and currency queues consist of lists of gallery submissions, ordered by newest first. Submissions can be further filtered by gallery.

### Log View

Each gallery submission has a separate sub-page dedicated to information related to its processing through the queue(s). This displays basic information about the submission, as well as (if enabled) currency reward information including responses to the form and the estimated reward as calculated when the submission was created (visible only to users with the Manage Submissions power). If a submission has been voted on, a record of vote(s) is visible to permissioned users as well. This page is visible only to the submitting user and/or any collaborators as well as users with the Manage Submissions power.

The page includes sections for comments between user(s) and users with the Manage Submissions power (staff), as well as for staff-only comments. The submitting user is notified when a new comment is made in the user-staff comment section.

### Approval Queue

Pending submissions can be acted upon, while approved and rejected submissions are for reference only. Pending submissions can be voted on either directly from the approval queue or on the submission's log view using the provided buttons. The submitting user will be notified when the submission is either approved or rejected.

### Currency Queue

Approved submissions that have not yet received rewards can be acted upon, while submissions that have already received rewards are for reference only. Currency is rewarded for submissions via the log view. If a gallery submission is eligible for currency rewards, a form will be made available listing the user and/or all collaborators as well as participants allowing the processing user to enter in the amount of currency each user involved should receive. Submitting this automatically distributes the respective amounts to the users and notifies them.

## See Also

- [Prompts](prompts.md)
- [Claims](claims.md)
- [Currencies](currencies.md)
- [Characters](characters.md)