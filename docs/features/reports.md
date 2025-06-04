# Reports

Reports are a submission type that accepts user content and bug reports into a queue. They can be viewed and processed in the admin panel by users with the **Manage Reports** [power](user-ranks.md).

## Submission

Reports can be submitted from the report submission page. A link to this is also available on the bug report index for logged-in users, and "report content" buttons are present on pages with user-submitted content.

A report requires:

- URL/Title
- Is/Is Not Bug Report
- Error Type (if bug report)
- Comments (no HTML)

**URL/Title** is a link to the offending content (content report) or a short summary of the bug (bug report).

**Is/Is Not Bug Report** is whether or not the report is a bug report. If this is enabled, an additional field for specifying the type of bug appears.

**Error Type** is the type of error being reported. By default, the options are: 500 error, 404 error, text error, exploit, or other error.

**Comments** are optional. This space can be used to describe/describe in further detail the nature of the report. Line breaks will be preserved, but HTML will not be rendered.

### Submission

Reports submitted to the queue cannot be edited by the user. The report will have its own page containing all submitted information. 

A report's visibility depends on its nature; content reports will not be visible to any users besides the submitter and users with the Manage Reports power. Bug reports, however, are listed publicly in the bug report index (to prevent duplicate reports). If an exploit has been reported, however, the report will be hidden until the report is closed (and the issue presumably addressed).

## Report Queue

Users with the **Manage Reports** power can view the queue, assign themselves to reports, respond via the comments system, and close reports.

The report queue consists of lists of submissions filtered by status, ordered by newest first. Pending reports can be acted upon, while closed reports are for reference only.

Clicking the edit button takes the user to the report review page, where they can assign, comment on, or close the report depending on its status.

### Assigning Reports

Newly submitted reports are "unassigned"; that is, there is no user assigned to handling them. Any user with the Manage Reports power can assign an unassigned report to themself. This removes the report from the main queue and places it into a special user-specific queue section that displays only the assigned reports for the currently logged-in user, the status of which is reflected on the admin index. Permissioned users may still view all current assigned reports via the queue.

### Processing

Open reports can be commented on by staff and user(s). This can be used to communicate with user(s) in order to facilitate addressing the subject of the report.

Once the subject of a report is resolved, it can be closed with staff notes as to any pertinent details, such as action taken. Once a report is closed, users will not be able to view comments on the report, though they will remain visible to staff, so any details that should be preserved from comments should be included in the staff notes.

## Bug Report Index

A site's bug reports are listed publicly in its bug report index. This list shows the title of the report, when it was submitted, and its status. This list may be searched by URL or title. Logged-in users may view the details of non-exploit bug reports; exploit reports, however, are hidden until they are closed to prevent abuse.