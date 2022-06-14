

## KBase Build & Release Guide

This guide describes how to set up and use the standard KBase build and release scripts.
These scripts allow KBase developers to:

- Automatically build test images when a pull request is created
- Tag images as `latest` once a pull request is merged
- Create production-ready images with semantic versions (e.g. `1.1.4`) using GitHub's [Release](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) process
- Enable repos to use optional fully automated [continuous deployment](https://en.wikipedia.org/wiki/Continuous_deployment) to development (e.g. `CI`) enviroments once these environments are deployed on Rancher2.

---

### Contents

#### Enable Build Workflows

  - [New Repository](./guide/new-repository.md)
  - [Existing Repository](./guide/existing-repository.md)

#### Enable Required Branch Rules

- [Enable `development` and `main`/`master` branch rules](./guide/enable-branch-rules.md)

#### 	Workflow Processes

- [Development Workflow](./guide/development-workflow.md)
- [Release Workflow](./guide/release-workflow.md)


---

## FAQ / TLDR

#### Q: How do I get docker images building in my repo?
A: Add the "Build Production Release Image" and "Pull Request Build, Tag, & Push" workflows from the [Github Actions Tab](https://github.com/kbase/.github/actions/new). Then [Enable `development` and `main`/`master` branch rules](./guide/enable-branch-rules.md)

#### Q: How do I deploy an docker image on ci?
A: Create a PR against "develop". Once the PR is merged into develop, you can deploy it on CI

#### Q: How do I deploy an docker image on the production environments?
A: Create a PR from develop to main, along with release notes and change logs. Upon merging to main, draft a release using semantic versioning
and update the release notes in github. Then ask in #devops to deploy the latest tag.

#### Q: How do I deploy an docker image on ci from a feature branch, without merging it in yet?
A: Either use the manual workflow or edit XXX


---
**|| Next: [New Repository](./guide/new-repository.md) ||**
