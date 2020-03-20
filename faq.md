# FAQ

## How to audit automatically

> We’ve been moving forward with SSO enablement, but have hit a wall running audits: as far as I know, we don’t have a way to audit API tokens, Auth tokens, or SSH keys. Can you please provide guidance?

Unfortunately, there is no reliable automated approach. The best strategy is to communicate intentionally and with plenty of time to the users to gather this information. Giving users clear instructions, and enough time, will provide the most accurate information. As you move forward, any incomplete information will become clear as users who did not respond or cooperate will lose access to GitHub.

## How to automate user provisioning

> My first goal with GitHub is to setup SAML authentication with OKTA and automate user provisioning. I would like to discuss and understand the setup best practices. Currently we invite existing accounts to our Org, and when they left, we remove them from Org. My concern is how to manage those users? What steps the user should take to avoid from losing they private GitHub account? (when they removed from org)

This is only possible with SCIM, which is only possible on GHEC with Azure AD, Okta, or OneLogin. [You can read more here](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/about-scim). In other circumstances, this must be done manually.

## How to manage service accounts?

Admins have several options to manage service accounts, including:
- [Adding service accounts as outside collaborators](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/adding-outside-collaborators-to-repositories-in-your-organization)
- Create a separate organization that isn't SAML enforced (GHEC only)
- [Allow built in authentication for users outside of your identity provider](https://help.github.com/en/enterprise/2.19/admin/user-management/allowing-built-in-authentication-for-users-outside-your-identity-provider) (GHES only)

## How to setup users account privilege?

This is best done by adding users to teams. This can be done automatically in some circumstances (AzureAD with team sync, or Okta to do automatically). Otherwise, users need to be added to teams in other ways.

One way to do this is through the [probot/invite-contributors](https://probot.github.io/apps/invite-contributors/) app.

## Does Azure AD team sync allow for syncing of groups and subgroups?

Syncing, yes. Team sync will flatten membership of subgroups. 

## Session time out

### What are the minimums and maximums for session length? Do we honor them on GHEC and GHES?

There is no enforced session minimum or maximum. We support SessionNotOnOrAfter attribute to set session lengths via the IdP.

### What if the IdP doesn't support a setting to enforce session length?

Use the 24 hour default, reach out to the IdP to make that request.