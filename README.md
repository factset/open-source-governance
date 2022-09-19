# Open Source Governance @ [FactSet](https://factset.com/)

**If you are an employee at FactSet, please refer to FactSet's _Open Source Code Use Policy_ on the corporate intranet, for details about our corporate policies with respect to Open Sourcing existing software, contributing to Open Source software during work, and contributing to Open Source software outside of work**

**This document is intended to capture our policies for maintaining Open Source projects under the _FactSet_ organization on GitHub.**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [Joining the FactSet Organization](#joining-the-factset-organization)
  - [Setup Two-factor Authentication](#setup-two-factor-authentication)
  - [Use Full Name in Your Profile](#use-full-name-in-your-profile)
- [Setup a Project](#setup-a-project)
  - [Developer Tooling](#developer-tooling)
  - [Developer Extensions](#developer-extensions)
  - [GitHub Labels](#github-labels)
- [Policies](#policies)
  - [Package Publishing](#package-publishing)
- [Common Issues](#common-issues)
  - [Disabling Two Factor Authentication](#disabling-two-factor-authentication)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Joining the FactSet Organization

There are a few tasks that will need to be completed prior to joining the FactSet organization as an employee or outside collaborator.

Some tasks are requirements stemming from corporate policies while others will improve your experience, and the experience of others in our organization.

### Setup Two-factor Authentication

> **Required**

Please setup your GitHub account with [2FA authentication enabled with GitHUb](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/).

### Use Full Name in Your Profile

<img align="right" alt="Mentioning an organization member." src="/images/mention.png">

On your [profile settings page](https://github.com/settings/profile) please use your full name on your public profile so that it's easy for members within the organization, and non-organization contributors, to find you.

An example of using a person's first name to discover them using [GitHub's _mention_ feature](https://blog.github.com/2011-03-23-mention-somebody-they-re-notified/).

## Setup a Project

Once you have a new project on FactSet's organization (created through FactSet's _Open Source Code Use Policy_ process), it's time to get your project setup with a few things to make your life easier.

### Developer Tooling

You may setup your project with several platforms to provide your team with feedback on code quality, security, team health, etc.

FactSet’s GitHub Admin team provides some support for the following platforms:

- GitHub, including (Please feel free to use any feature available in GitHub Enterprise Cloud)
  - [GitHub Actions](https://docs.github.com/en/actions)
- Automated Dependency Updates - [Renovate](https://github.com/marketplace/renovate)

### Developer Extensions

To further improve your productivity consider installing the following browser extensions:

- Inline Code Intelligence - [Sourcegraph](https://about.sourcegraph.com/)

### GitHub Labels

To help with issue and pull request management, we recommend a set of [GitHub Labels](https://help.github.com/articles/about-labels/) in this project's [`labels.json`](./labels.json) file.

To deploy these labels to a project, we recommend using a tool called [`@hutson/github-metadata-sync`](https://www.npmjs.com/package/@hutson/github-metadata-sync), download the `labels.json` file (or clone this repository), and run the following:

```bash
github-metadata-sync --config labels.json --token [PERSONAL ACCESS TOKEN]
```

> **Note:** Please create a [_Personal Access Token_](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/) with repository access to all repositories listed in the `labels.json` file and pass that token to the `--token` flag.

## Policies

### Package Publishing

All packages published to a third-party package repository such as Nuget, Npm, PyPI, etc., from a FactSet Open Source project on `GitHub.com/factset` must be published under an account owned and managed by FactSet’s Open Source Committee (OSC).

_If you do not intend to publish your project to a third-party package repository, or don't plan to at this time, then no action is required on your part._

Our policy is to ensure our company retains control over the published package for the duration of its use at FactSet.

We currently support publishing under accounts for the following package repositories:

- [Npm](https://www.npmjs.com/~fds)
- [PyPI](https://pypi.org/user/factset/)

We are adding support for additional package repositories: including Conan, Nuget, Circle CI Orbs, and Maven. If we’re not supporting a package repository that you need, please _@mention_ the [`@cid-support`](https://github.com/orgs/factset/teams/cid-support) team.

Though you are publishing under an account managed by the OSC, you may continue to manage your release workflow, deciding when its best to publish a new version of your project.

## Common Issues

While working on Open Source projects under the FactSet organization you may encounter the following common issues.

### Disabling Two Factor Authentication

In the event that you disable, and then re-enable, 2FA, please reach out to a member of the organization to be re-invited.

[According to GitHub](https://help.github.com/articles/disabling-two-factor-authentication-for-your-personal-account/):

> Warning: If you're a member, billing manager, or outside collaborator to a public repository of an organization that requires two-factor authentication and you disable 2FA, you'll be automatically removed from the organization, and you'll lose your access to their repositories. To regain access to the organization, re-enable two-factor authentication and contact an organization owner.
