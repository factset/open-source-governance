# Developer Tooling

## Table of Contents
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Continuous Integration and Delivery](#continuous-integration-and-delivery)
  - [Circle CI](#circle-ci)
    - [Delivery (GitHub interaction)](#delivery-github-interaction)
    - [Deployment (Publishing)](#deployment-publishing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Continuous Integration and Delivery

FactSet’s Continuous Integration and Delivery (CID) team provides some support for using the [Circle CI](https://circleci.com/) platform for continuous integration and deployment of FactSet Open Source projects.

CID support includes:
- Addressing connection issues between GitHub and Circle CI.
- Guidance on employing CI best practices with Circle CI.
- Setup and support for deploying packages to artifact repositories; such as [Nuget](https://www.nuget.org/), [Npm](http://npmjs.com/), [PyPI](http://pypi.org/), etc.

You may choose to use another CI platform, such as [Travis CI](https://travis-ci.com), but please understand that we only provide very limited support (at most: addressing connection issues and providing credentials for publishing packages).

### Circle CI

> Please see Circle CI’s excellent [_Getting Started Introduction_](https://circleci.com/docs/2.0/getting-started/) guide.

#### Delivery (GitHub interaction)

If you would like to interact with GitHub from Circle CI with the goal of creating tags, uploading build artifacts, etc., you may use our `github-interaction` [Circle CI context](https://circleci.com/docs/2.0/contexts/).

Our context exposes the following environment variables:
-	`GITHUB_TOKEN` - For our [`factset-bot`](https://github.com/factset-bot) account.

#### Deployment (Publishing)

According to our [Package Publishing](./README.md#package-publishing) policy, all package publishing must be published under an account owned and managed by FactSet’s Open Source Committee (OSC).

You may access the appropriate publishing credentials using our `package-publishing` [Circle CI context](https://circleci.com/docs/2.0/contexts/).

Our context exposes environment variables for the following package repositories:

- [Npm](https://www.npmjs.com/~fds)
  - `NPM_TOKEN`
- [PyPI](https://pypi.org/user/factset/)
  - `PYPI_PASSWORD`
  - `PYPI_USERNAME`

Here’s an example using Circle CI to publish an npm package to the public npm registry every time a new git tag is created on GitHub:

```
jobs:
  deploy:
    image: node:10
    steps:
      - checkout
      - run: yarn install --frozen-lockfile
      - run: $(yarn bin)/npm-publish-git-tag

workflows:
  version: 2
  deploy:
    jobs:
      - deploy:
          context: package-publishing
          filters:
            branches:
              ignore: /.*/
            tags:
              only: /.+/
```
