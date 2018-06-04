# Open Source @ FactSet

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [Joining the FactSet Organization](#joining-the-factset-organization)
- [Setting Up a Project](#setting-up-a-project)
  - [JavaScript Project](#javascript-project)
- [Common Issues](#common-issues)
  - [Disabling Two Factor Authentication](#disabling-two-factor-authentication)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Joining the FactSet Organization

There are a few requirements prior to a FactSet employee joining the FactSet organization on GitHub.

Requirements:
* Must have [2FA authentication enabled with GitHUb](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/).
  * This is part of our continued efforts to improve the security of FactSet's Open Source efforts.

## Setting Up a Project

Here are our recommendations for workflow integrations when setting up a new project in FactSet's organization.

### JavaScript Project

* Continuous Integration - https://github.com/marketplace/circleci
* Code Coverage Reports - https://github.com/marketplace/codecov
* Automated Dependency Updates - https://github.com/marketplace/renovate

## Common Issues

### Disabling Two Factor Authentication

[According to GitHub](https://help.github.com/articles/disabling-two-factor-authentication-for-your-personal-account/):

> Warning: If you're a member, billing manager, or outside collaborator to a public repository of an organization that requires two-factor authentication and you disable 2FA, you'll be automatically removed from the organization, and you'll lose your access to their repositories. To regain access to the organization, re-enable two-factor authentication and contact an organization owner.

In the event that you disable, and then re-enable, 2FA, please reach out to a member of the organization to be re-invited.
