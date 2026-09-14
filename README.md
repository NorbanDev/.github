# NorbanDev/.github

Default issue forms, PR template and the issue writing guide for every NorbanDev repository.

**This repository is public**, because GitHub only applies defaults from a public `.github` repository. The defaults still apply to private repositories. Put nothing here that is not fit to publish.

| File | What it does |
|---|---|
| `.github/ISSUE_TEMPLATE/` | The Bug, Feature and Task forms, and `config.yml` |
| `.github/pull_request_template.md` | The PR template for repositories without their own |
| `ISSUES.md` | How to write an issue |

## How the defaults apply

- A repository uses these files only for the file types it does not define itself.
- **Issue templates are all or nothing.** A repository with any valid file in its own `.github/ISSUE_TEMPLATE/` folder uses none of the forms here. Do not add one without a reason that holds for that repository alone.
- A repository's own `pull_request_template.md` replaces the one here. Keep one only for checks specific to that repository, such as a `tofu plan` summary or screenshots.

## Changing a form

A change here reaches every repository at once. Open a PR, and name in it the repositories and automations that read the changed field, such as NorBot's issue format.
