# Design Updates

Design updates are a means by which users can upload and submit an updated version of their [character](characters.md)'s design, or a completed [MYO slot](myo-slots.md) design for review. This system streamlines the process of uploading new images for the masterlist by having users prepare the images and fill in the character stats, and submissions go into a review queue where staff can act upon them.

## Usage

Users are able to prepare a new approval request for a character or MYO slot by going to their character/slot's page and clicking on Update Design or Submit MYO Design respectively.

At this point, if the `is_design_updates_open` [site setting](site-settings.md) is set to 0, the user will not be able to create a new request. However, if it is set to 1, the page will prompt the user to create a new request if one does not exist, or to view the request if there is already an active one. Clicking on the button creates a new draft for a design update approval. After each section of the approval has been updated, it can be submitted to the queue.

Note that characters or MYO slots with an active request cannot be transferred or traded, due to complications that may arise from attached resources. At the draft stage, a design approval request can be deleted easily.

Once the request has been submitted to the queue, staff with the **Manage Masterlist** [power](user-ranks.md) can choose to approve, reject or cancel the request. The effects of each action are covered further below.

## Submission

The approval request page contains the following tabs: Status, Comments, Masterlist Image, Add-ons, Traits.

**Status** shows the current status of the draft, and notes if any of the required information is missing. It also allows users to delete the request (the current draft), or submit it if it's ready. All of the sections below must have been edited at least once for the user to submit their request, regardless of whether any information has been entered (for the optional fields).

**Comments** is a section for the user to include any notes about the submission, if required by staff.

**Masterlist Image** allows the user to upload an image and use the thumbnail cropper to crop it. The image thumbnail can be edited by staff during approval, if necessary. The user can also add image credits for the designer(s) and artist(s) of the image.

**Add-ons** allows the user to choose items and currencies from their inventory/bank to submit with the request. These items and currencies will be removed from their inventory/bank immediately, but returned if the user decides to cancel.

**Traits** allows the user to select the [species](species.md), subtype, [rarity](rarities.md) and [traits](traits.md) for their character. If the user is submitting for an MYO slot, any restrictions on these fields will be applied here - for example, compulsory traits cannot be deselected, and if the species is fixed, it cannot be changed here.

After the information on each tab has been saved once, the slot can be submitted. At any point during the editing of this draft, the page can be viewed by a user with the **Manage Masterlist** power - this can be used for obtaining feedback on the current design without having to submit it.

## Approval Queue

Users with the **Manage Masterlist** power can view the queue and approve/reject/cancel submissions in the design update approval queue.

The staff member reviewing the submission cannot modify any of the trait information the user has submitted - this is so the submitter does not end up with traits different from what they expected to receive. However, the staff member can:

- Re-crop the thumbnail
- Upload a new thumbnail
- Change the designer/artist credits of the image

#### Voting

Voting on design updates may optionally be enabled via the extensions [config file](config-files.md). This allows users viewing design updates in the approval queue to vote to approve or reject/cancel a design update. This is only a communication tool for sites' staff and does not automatically perform any actions when a consensus has been reached.

### Approve

Approving the request requires some data about the character to be added (in the case of MYO slots) or reviewed:

- Character Category
- Number
- Character Code
- Description
- Is Giftable
- Is Tradeable
- Is Resellable
- Resale Value
- On Transfer Cooldown Until
- Set Active Image
- Invalidate Old Image

**Character Category** ~ **On Transfer Cooldown Until** are covered in the [Characters](characters.md) article.

**Set Active Image**, if set to On, will cause the newly-uploaded image to become the character's new masterlist image.

**Invalidate Old Image**, if set to On, will mark the character's old masterlist image as invalid. See the [Character Images](character-images.md) article for more information.

### Reject

Rejecting the request hard denies the update, causing all items and currency attached to it to be returned to the user, and forcing them to need to create a new request if they want to update the same character.

A comment can be added to the rejection, which the user will be able to see on the request page.

If a softer approach is desired, consider cancelling the request instead.

### Cancel

Cancelling the request puts it back into draft status, allowing the submitter to make changes to their submission and resubmit it.

A comment can be added as feedback, which the user will be able to see on the request page. Additionally, a toggle is provided for preserving the user's position in the queue - if set to On, when the user resubmits the request, it will be inserted back into the queue at the position it was at previously, allowing the submitter to avoid having to wait for their turn again.

## See Also

- [Character Images](character-images.md)
- [Characters](characters.md)
- [MYO Slots](myo-slots.md)