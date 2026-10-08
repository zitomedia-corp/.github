# Creating repositories and giving access

For the organization owners of `zitomedia-corp`.

## New repositories

- Create each repository from the `zitomedia-corp/project-template` template: "Repository template"
  on the New repository page, or "Use this template" on the template's page. Leave "Include all
  branches" off. ([GitHub guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template))
- Owner `zitomedia-corp`, visibility Private.
- Add a description saying what the repository does, without person or company names.

## Giving someone access

- Grant access per repository, from the repository's Settings → Collaborators and teams → Add people.
  Organization membership grants no repository access.
  ([GitHub guide](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization))
- Invite the person's own GitHub account, never a shared one.
- Give **Write** by default, or **Maintain** to someone who looks after the repository (releases,
  settings such as features and merge options). Maintain cannot delete the repository or change access.
- Give **Admin** to no one outside the organization owners. Repository admins can invite outside
  collaborators, and the Free plan has no setting to stop them.
- The organization requires two-factor authentication with a secure method (authenticator app,
  passkey, security key or GitHub Mobile). An account without it cannot accept the invitation, and
  one that later uses text-message codes only loses access.
