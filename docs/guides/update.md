# Updating Lorekeeper

!!! info

    This is a general guide on how to update Lorekeeper. See the [v2 Upgrade Guide](upgrade.md) for information on updating to Lorekeeper v2 specifically.

Lorekeeper is continuously undergoing new development-- bugs being fixed, new features being worked on and added. When ready, these updates make their way to the [GitHub repository](https://github.com/lk-arpg/lorekeeper) by being merged into one of its branches, where they become available to you to update your own site with! However, for ease of development, greater consistency and stability in releases, and general organization, Lorekeeper is split into different branches. This may make it difficult to tell at first glance which branch you should update your site with; however, this can also help ensure you get the right updates.

If you're not familiar with git, consider reading [Tutorial: Introduction To Git](https://wiki.lorekeeper.me/index.php?title=Tutorial:_Introduction_To_Git) first! This article assumes a basic knowledge of git. Also see [Tutorial: Installing Extensions](https://wiki.lorekeeper.me/index.php?title=Tutorial:_Installing_Extensions) as the process of pulling, etc. updates themselves, managing any merge conflicts, and so on also applies here!

If you yourself are interested in contributing to Lorekeeper, meanwhile, please read the [Contribution Guide](../contributing.md)! It covers similar material but focuses on the development side of the material instead.

## Branches & You

The core Lorekeeper repository, or repo, has several different branches corresponding to different kinds and stages of development. There are two that are always present:

- `main`, which always has the latest **stable release** of Lorekeeper. You can always pull this!
- `develop`, which always has the latest updates and new features, but this means it's the **least stable**. You can always pull this, but be aware that changes will be more frequent and bugs more likely!
    - As a general rule of thumb, it's recommended to only pull develop if you are confident in the ability of yourself or someone on your team to both resolve any bugs or issues that come up (as these may be specific to your site, depending on any existing modifications) *and* report (or, more ideally, contribute fixes for) any issues that are present in an **clean, unmodified** copy of the `develop` branch.

"Stable", here, means that **no new features are being added**. Any change in the code in `main`, for instance, comes from either a new release or hotfix (which are only for critical issues!). This also tends to mean fewer bugs, as ideally most are caught and fixed before a a new version is released, and the lack of change means new bugs don't occur. Conversely, `develop` is the exact opposite: it always has the latest features, updates, etc.! Of course, this means that it always has the latest bugs. Similarly, new releases-- or updates to `main`-- happen relatively infrequently, while `develop` may be updated and added to at any time!

There are also three different *types* of branches. Branches of these types are temporary, and used primarily to keep code organized before it is merged into another branch. These types are:

- Release Branches
    - These follow the naming scheme `release/UPCOMING-VERSION-HERE`.
    - These contain a stable version of an upcoming release-- again, this means no new features are being added!-- that is in testing so that bugs can be fixed before it becomes the current release.
    - **If a release branch exists, it's ok to pull!** In fact, it's helpful to do so if you're willing to report bugs, as catching and reporting them helps get them fixed-- and that helps ensure the upcoming release behaves as intended!
- Feature branches
    - These follow the naming scheme `feature/FEATURE-NAME-HERE`.
    - These contain new features or bugfixes. These are made by contributors so as to keep proposed changes to Lorekeeper isolated so that they can be reviewed and, if/when they are approved, merged into another branch.
    - **Do not pull these!** There is no guarantee that the code in them is ready for use and you are liable to break your site if you merge their contents into your site prematurely.
- Hotfix branches
    - These follow the naming scheme `hotfix/HOTFIX-NAME-HERE`.
    - These contain emergency bugfixes, e.g. fixes for critical issues or security vulnerabilities.
    - **Do not pull these!** There is no guarantee that the code in them is ready for use and you are liable to break your site if you merge their contents into your site prematurely. They will be merged into main if/when they are approved.

### Which branch do I pull?

The answer to this question depends on whether you really need the latest features and/or how willing you're willing to handle potential bugs/bug reports, as well as how often you want to update your site. In summary:

- `main`
    - Most stable
    - Updates least frequently
    - Ideally, has the least bugs!
- (If one exists) the current release branch
    - Stable
    - Release branches occur infrequently, and update with bugfixes as they are contributed
    - Has a variable but diminishing number of bugs, generally
- `develop`
    - Least stable
    - Updates most frequently
    - Liable to have the most bugs!

Regardless of which you choose, remember that you only need to pull one of them to receive all relevant updates for that branch! That is, any updates from one branch that apply to another will always be merged into the latter branch by contributors-- so if there is, for instance, a hotfix that is merged into `main`, but you are currently pulling the latest release branch, you don't need to pull `main` as well; the hotfix will also be merged into the release branch!

## Update Announcements

Each Monday-- assuming there are updates to report-- an announcement of changes made over the course of the week is posted to the Announcements channel of the [Lorekeeper discord server](https://discord.gg/U4JZfsu).

These announcements are broken down by branch (if multiple branches have been updated) and then broken down into three types of change:

- New features (Added)
- Miscellaneous changes (Changed)
    - These tend to be smaller tweaks that aren't new features in themselves nor bugfixes, but are nonetheless improvements!
- Bugfixes (Fixed)
    - These are expressed via *what bug was fixed* (rather than what change was made to fix the bug), for clarity.

Additionally, any commands that must be run or other actions relating to updating are listed alongside the updates (for each branch, if there are multiple). If an announcement does not specify the branch updated, assume it's `develop`; it's this branch that sees the most/most frequent updates, as it can potentially be updated continuously.

**Of course, always make sure to read and follow all instructions provided!** This helps ensure that you update your site successfully and without incident!

## See Also

- [Contribution Guide](../contributing.md)