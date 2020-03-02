To be shared (before? during? after?) Engineer managers meeting

----

Dear Engineering Managers,

As the GitHub Administrators (+ SAML administrators, + IT Security team), we are planning a roll-out of SAML authentication with GitHub Enterprise. This will take place over the next 6 weeks. We would like to share the anticipated plan, to ensure the smoothest transition possible.

#### Why are we doing this?

SAML is a secure authentication method with many benefits to our organization. We already have SAML configured for some of our services. To maximize the benefits and security, we will be configuring SAML with GitHub Enterprise.

#### How will engineers be affected

Once we start this process, GitHub users will need to authenticate to GitHub through SAML. There will be a short window to do this before SAML authentication is enforced, so it is very important to do this promptly.

We will also need to identify and manage all service or bot accounts. Engineers are responsible for communicating these accounts with us, so we can grant then the proper access and their use can continue uninterrupted.

#### Timeline

For a detailed view, please see the roll-out plan.

Most important events to be aware of are:

- Week 1
  - Admins communicating with managers
  - **Managers to share any important information, including potential beta user groups with admins**
- Week 2
  - Admins communicating with engineers in week 2
  - **Users to share admin access information, and bot/service account information with admins**
  - Admins configure SAML in testing environment in week 2
- Week 3
  - Admins to configure in production in week 3
  - Admins to enable first test users in week 3
- Week 4
  - Admins to mark bot users as outside collaborators, remove inactive admins, bots, and users in week 4
  - Admins to enable SAML authentication with GitHub for all users in week 4
- Week 5
  - **All users must authenticate with SAML to maintain access in week 5**
- Week 6
  - Admins to enforce SAML authentication with GitHub in week 6

#### Action needed

We are looking for a team of engineers to be the first onboarded group. If your team would be willing to help us with this and gain access to SAML authentication sooner, please respond with more detail to this email.

Please share this with your teams as you see fit. We will be contacting engineers directly next week to share the rollout plan and gather information about bot/service and admin accounts.

You may be aware of other influences that could impact the transition. If there is any additional information that we should be aware of, please alert us immediately.