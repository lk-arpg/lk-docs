# Working with Multiple Developers

When collaborating with multiple developers on a Lorekeeper project, it's essential to establish clear guidelines and best practices to ensure effective collaboration and minimize conflicts.

## The Golden Rules

These are written in absolutes, but they are just guidelines to help you and your hired devs work effectively together. Feel free to use as many or as little as you like, whatever works best for your team!

### **For the Project Manager / Lead:**

- Define clear tasks for each developer. Set deadlines as needed.
- Use a shared repository separate from your production site (e.g. GitHub).
- Use a kanban board or similar tool to track progress and tasks. (ex. Trello, GitHub issues, Discord threads, whatever works for your team)
- If possible, limit access to your live site to only those who absolutely need it.
    - Why limit access? Unfortunately, bad actors exist. The fewer people with access, the lower the risk of something going wrong.
- Enforce code reviews and testing before merging changes.
    - Use the following template if you'd like:
    ```md
    - **Purpose of Changes:** Briefly describe what this change is intended to accomplish.
    - **Issue Link (Optional):** Link to the relevant issue or task description.
    - **Screenshots (if applicable):** Include any relevant screenshots or visual aids.
    - **Additional Notes:** Any other information that reviewers should be aware of.
    ```

!!! info "Think of it like this:"
    Just like how we have at least two people review MYOs to make sure it's correct, having a second set of eyes review code changes helps catch mistakes, improve code quality, and share knowledge among the team.

    !!! warning
        This is not a substitute for proper testing. All changes should be tested in a development/staging environment before being merged.

        **Note:** Not all developers have the experience or time to review code. If you expect code reviews, make sure your team is on board and has the capacity to do so.

#### Environments

Most Lorekeeper projects will have at least two environments, it's good to at least be familiar with the concepts:

- Local / Dev — each dev works on their own machine.
- Staging / QA / Testing — a shared testing environment. Many sites WILL NOT have a staging environment.
- Production / Live — the site your users see and interact with.

---

### **For the Developers:**

- All work happens in a hosted repository (e.g. GitHub), NOT the live site.
- Use branches for every change, no exceptions.
- Nothing goes straight to “live”. NEVER MODIFY CODE DIRECTLY ON LIVE.  
    Changes flow:
    feature branch → pull request → review → staging (optional) → production.
- When possible, get features reviewed by at least one other person. It's not just about code quality, but also about shared knowledge. It makes it harder if only one person knows how something works.
- Small, frequent pull requests beat big ones that are hard to review.
- Write clear, descriptive commit messages. We recommend using the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) format.
- Definition of Done = works as described, tested, and documented. Make sure you ask for clarification if something is unclear.
- Communicate with your team if something is blocked or taking longer than expected.
- Write things down (how to run, how to deploy, what changed...)

## Branching Strategy

`main` — production-ready code.  
`dev` — integration branch if lots of parallel work.  
`feature/<short-name>` — one branch per feature (e.g., `feature/character-subtypes`).  
`hotfix/<short-name>` — for urgent production fixes.  

