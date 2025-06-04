# Contributing to Lorekeeper

Lorekeeper, much like any project in its vein, thrives on community contributions; be they bugfixes, new features, extensions, or so on, these efforts are what help make the project shine. If you are interested in contributing to core Lorekeeper, pull requests (or PRs) are always open at the [GitHub repository](https://github.com/lk-arpg/lorekeeper). If you have not already done so, a good first step is making a fork of the repository on your own account via the button on the upper right hand side of the page.

As a rule of thumb, we welcome PRs containing:

- Bugfixes (always!)
- Small features or quality-of-life additions
    - The rule of thumb for this is that the feature should relatively small in scale/compact, and either
        - Broadly useful to all users of Lorekeeper, or
        - Useful to most, but not all, users of Lorekeeper but wholly optional.
            - If your feature is compact enough to do so it is encouraged in this instance to create a toggle for it in `config/lorekeeper/extensions` that controls whether it is enabled or not.

If you're unsure of what to work on, take a look at the current [issues](https://github.com/lk-arpg/lorekeeper/issues) listed on the repo. These are labeled in accordance with their nature/contents (bug, feature request, etc.) and various other qualities (for instance, being a good first issue)!

## General Architecture

Generally speaking, Lorekeeper and its branches are structured and maintained in keeping with [GitFlow](https://datasift.github.io/gitflow/IntroducingGitFlow.html). Loosely, this means that there are two persistent branches:

- The default/primary branch-- `main`, in this case-- which always contains the current release/the current stable version, and
- The development branch-- `develop`, in this case-- which always contains the latest work-- features, fixes, and so on. It is by definition unstable.
    - This branch is itself off of `main` and in the infrequent but possible event that the latter is updated directly (i.e. via a hotfix), `main` will be merged into it.

As well as three *types* of branches; each branch of these types is destined to be merged into another and is important but ultimately impermanent:

- Feature branches
    - These follow the naming scheme `feature/FEATURE-NAME-HERE`, e.g. `feature/two-factor-auth`.
    - While these are called feature branches, they can contain new features and/or non-emergency bugfixes!
    - New features are **always** merged into `develop` and `develop` only.
    - These branches are created branched off of `develop` (if they contain features or there is no current release branch) or the current release branch (if there is one, and the feature branch contains only bugfixes for the current content within it).
- Release branches
    - These follow the naming scheme `release/UPCOMING-VERSION-HERE`, e.g. `release/v2.0.0`.
    - These are created by a maintainer of the repo when an upcoming release is feature-complete or otherwise ready, and are branched off of `develop`.
    - Once they are created, **no additional features or work from `develop` will be merged into these branches**, only bugfixes for the features already in them.
    - Conversely, bugfixes for features contained in a release branch are merged **directly into the release branch and the release branch only**. In the event that a release branch receives bugfixes, said release branch is periodically merged back into `develop` to incorporate them.
    - In essence, the purpose of a release branch is to isolate, test, and if necessary fix a static set of features.
    - When a release branch is sufficiently stable and any necessary preparations complete, the branch will be merged into `main` and become the new current release.
- Hotfix branches
    - These follow the naming scheme `hotfix/HOTFIX-NAME-HERE`.
    - These contain emergency bugfixes, such as fixes for critical issues or security vulnerabilities.
    - These are directly branched off of `main`/the current release and merged back into `main` when complete.
    - In such an event, `main` is merged back into `develop` as well to incorporate fixes.

### Code Styling

Contributions to Lorekeeper are recommended to follow the style of the project's existing code. However, PHP styling will automatically be adjusted for contributions on creation of a pull request or subsequent merge commit. If you wish to apply these changes locally, you can run or dry-run them via:

- Run with `composer lint`
- Dry run with `composer sniff`

### Branches and You

In summary:

- When contributing to Lorekeeper, you will create either a feature or (more rarely) a hotfix branch.
- If you are creating a new feature, **it must be isolated in its own feature branch** and a PRed into `develop`.
- If you are fixing bug(s), there are a few possibilities depending on the circumstances:
    - If there is currently a release branch, make a feature branch off of the release branch or check out the release branch itself.
        - Once you have done so, fix bug(s) with the current content of the release branch, then push the branch to your fork and make a PR to the release branch.
        - **Prioritize fixing bugs in the release branch first and foremost.** This allows the branch to better achieve stability and move toward full release.
    - If there is not currently a release branch, or if your fix(es) concern content that is **only** present in `develop`, make a feature branch off of `develop` or check out `develop` itself.
        - **Alternately put: do not PR bugfixes that apply to an extant release branch to `develop`.** Isolate them from any changes relevant only to `develop` on a branch created from the release branch and PR them to the release branch. This helps the release branch achieve stability and move toward full release.
    - As a general rule, making feature branches for bugfixes vs. checking out `develop` or the release branch and committing them directly is recommended, but not required, as you will need to push the relevant branch to your fork and make a PR regardless.
    - If you are making a hotfix for a critical issue present **in the current release**, create a new hotfix branch off of `main`, make the necessary changes, and PR it back into `main`.

### Git-flow in Sourcetree

If you are on a Windows machine, you will likely be using Sourcetree as your git client. Sourcetree has built-in support for this sort of branch structure accessible via the "Git-flow" button in the upper right hand corner of the program interface.

- You should first check out `main` and `develop` if you have not already. You may name `main` something else if you have a branch with that name that has contents other than/in addition to the current release.
    - If these branches are not present when you initialize the feature, - Sourcetree will attempt to create them using assumptions that may or may not be correct depending on how your local repo is structured; it is simplest to already have them present with their correct content beforehand.
    - This also has the advantage of them tracking the associated remote branches by default.
- Click the "Git-flow" button. It will ask you for the names of these branches and branch types.
    - As of the time of writing you do need to change these from the defaults to be consistent with the core repo.
    - If your local copies of `main` or `develop` have different names than these, change the production and development branch names to the names of your respective local branches.
    - Do not change the prefixes used for the three branch types.
- When you are ready, click "ok". Sourcetree will initialize the feature.

Now when you press the Git-flow button, a small panel will appear with suggested actions. By default these include "Start New Feature", "Start New Release", and "Start New Hotfix". As detailed above, the first and last options are the most relevant; clicking one of these will take you to a panel asking for the name of the branch (not including the prefix, which it will add automatically!) and what branch it should start from.

Please note when using this feature that you will need to push and PR your feature or hotfix branch itself and cannot use the "Finish Feature/Hotfix" option that Sourcetree offers.

## Making a Pull Request

Once you have made your branch containing your feature or fixes, tested it (at minimum locally!), and pushed it to your fork on GitHub, make a pull request. This, in essence, is a request for the contents of your branch to be integrated in the branch you make your PR to.

An easy way to do so is by navigating to the branch on your fork. Displayed above its contents/files will be a header stating "This branch is (number) commits ahead of lk-arpg:main" or similar; click "contribute", then click "open pull request". This will take you to the form to do so.

Once you are at this form, you will want to:

1. Ensure you are submitting the PR to the correct branch on the repo-- `develop`, the release branch, or `main`-- depending on which you branched from.
2. Enter a succinct and descriptive title for your PR.
3. Provide a description. You should list any bugs you have fixed, mentioning issue(s) if they exist, or explain (in detail!) the nature of an added feature.
    - Be sure to include any commands (such as `php artisan migrate`) which must be run as a consequence of your changes.
    - If in doubt, provide more information, not less! It isn't always easy to tell from code alone what the purpose of a change is, so you should explain as best you can.
4. Submit your PR!

Once your PR is submitted, it will be processed and reviewed by maintainers of the repo and members of the community. If/when there is a consensus on its approval, it will be merged in; at this point you can safely delete the branch on your fork if applicable/desired.