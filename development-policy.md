# Working in the Zito Media GitHub organization

Zito Media owns the source code of every project built for it. This page applies to everyone who
works in `zitomedia-corp`: Zito staff and contractors.

## Where code lives

- All code built for Zito lives in a `zitomedia-corp` repository, from the first commit.
- Repositories are private unless Zito approves otherwise.
- Personal accounts and other organizations hold copies at most, never the only copy.
- Each repository has a description saying what it is, and a README covering what it does,
  how to run it and how it deploys.

## Access

- Your Zito contact requests access for you. Access is granted per repository.
- Contractors receive **Write**, or **Maintain** when they manage releases. Admin stays with Zito's
  organization owners.
- Use your own GitHub account. Shared accounts are not granted access.
- Turn on two-factor authentication on your GitHub account.
- Access ends when your contract ends: your Zito contact tells the organization owners that day.
  Access is reviewed every quarter.

## Branches and pull requests

- Work on a branch named by type: `feat/`, `fix/`, `refactor/`, `chore/`, `docs/`, `test/`, `perf/`,
  then a short kebab-case name (`fix/invoice-total-rounding`).
- Merge to `main` through a pull request, using the template that opens with it.
- On a repository with one developer, direct pushes to `main` are fine.
- Keep `main` deployable. Never force-push to `main` or delete it.
- Keep the pull request description short enough to read in a minute. Say why, not what each line does.

## Commit messages

- Format: `type: summary`, using the branch types above (`fix: round invoice totals to cents`).
- Write the summary as a command, in lowercase, under 72 characters, with no period.
- One logical change per commit.
- Add a body only when the reason is not obvious: two or three lines on why.

| Good | Bad | Why it is bad |
|---|---|---|
| `fix: round invoice totals to cents` | `Fixed invoice bug` | Past tense, no type, does not say which bug |
| `feat: add install date to sales review` | `feat: Added a new feature that allows users to see the install date on the sales review page.` | Past tense, capitalized, over 72 characters, with a period |
| `chore: pin node to 20 in ci` | `update` | Says nothing |
| `refactor: move pricing rules into one module` | `refactor: various improvements and cleanups` | Vague; a reader cannot tell what changed |
| `fix: stop duplicate orders on retry` | `fix: duplicate orders` + a 20-line body listing every file touched | The diff already shows the files; the body is for why |

A body, when one helps:

```
fix: stop duplicate orders on retry

The app resent orders the server had already saved.
Orders now carry an id, and the server ignores repeats.
```

## AI coding tools

- Copy the branch, commit and pull request rules above into your tool's instruction file
  (`CLAUDE.md`, `AGENTS.md`, `.cursorrules` or similar).
- Review what the tool writes before you commit it, including the message.
- Use AI tools only with model training on your Zito work turned off. For GitHub Copilot: Settings →
  Copilot → "Allow GitHub to use my data for AI model training" → Disabled.

## Secrets

- Never commit passwords, API keys, tokens or service-account files. Store them in GitHub Actions
  secrets or the cloud provider's secret manager.
- If a secret reaches a commit, rotate it at once and tell your Zito contact. Deleting the commit
  leaves the secret in history.
- Deploy and hosting accounts belong to Zito, not to an individual.

## When your work ends

- Merge or close your open branches and pull requests.
- Hand over to your Zito contact anything the project needs that sits outside the repository:
  hosting, databases, domains, third-party accounts.
