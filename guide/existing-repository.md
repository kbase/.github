## Existing Repository

**Contents**

- [Preliminary Steps](#preliminary-steps)
- [Add Actions To Repository](#add-actions-to-repository)
   -  [Existing Repo Demo](#existing-repo-demo)
- [Next Steps](https://github.com/jsfillman/kbase-build-guide/blob/main/guide/existing-repository.md#next-steps)
---


### Preliminary Steps 

1. Ensure that your repo contains the following up-to-date branches:
   - `main` or `master`
   - `develop`
   - `inbox`
2. Review your current repo's `.github/workflows/` directory if one currently exists.
3. Ensure there are no files named `pr_build.yml` or `release-main.yml` in the `.github/workflows/` directory.
   - If these files aleady exist, they can't be added using the [Add Actions To Repository](#add-actions-to-repository) steps below.
   - If these files match the current stock [pr_build.yaml](https://github.com/kbase/.github/blob/main/workflow-templates/pr_build.yaml) & [release-main.yml](https://github.com/kbase/.github/blob/main/workflow-templates/release-main.yml), these workflows are already enabled, and you can skip to the [Enable Branch Rules](enable-branch-rules.md) section.
4. Review any other .yaml/.yml files in `.github/workflows/` to ensure they aren't redundant or are causing unnecessary failed builds.

### Add Actions To Repository

To enable the KBase build scripts on an existing [github.com/kbase](https://github.com/kbase) repo, simply:

1. Navigate to the `Actions` tab on any repository in the `kbase` organization.
2. If there are any existing Actions (workflows) enabled, click on the `New workflow` button above the list of active workflows.
   - If the repo does not have any active Actions (workflows), then a `Get started with GitHub Actions` page will appear instead.
3. Navigate to the `By KBase Software` section.
4. Click `Configure` under the `Pull Request Build, Tag, & Push` Action.
5. Click `Start commit` to add the file `pr_build.yml` to the **main** or **master** branch of the repo.
6. Repeat steps 1-5 to add the `Build Production Release Image` (`release-main.yml`) Action to the **main** or **master** branch of the repo.
7. Optionally, repeat steps 1-5 to add the `Manual Build & Push` (`manual-build.yml`) Action to the **main** or **master** branch of the repo.
8. Use pull requests to propagate the workflow files to all active branches including: 
   - `main`/`master` 
   - `develop`
   - `inbox`
   - Any active feature branches

| ⚠️ These workflows must be merged to _all_ active branches for full functionality! |
| :----------------------------------------------------------: |

##### Existing Repo Demo

<!-- This code creates a simple dropdown -->
<details>
<summary>Expand For Demo</summary>

![ExistingRepo](https://user-images.githubusercontent.com/6155956/164335446-ae459f62-28e6-4089-9acb-4e22719e83be.gif)

</details>

---

### Next Steps


Before using these actions, please:

1. Review the [Development Workflow](development-workflow.md) and [Release Workflow](release-workflow.md) sections.
2. Enable the required [branch rules](enable-branch-rules.md) and [status checks](enable-branch-rules.md#require-status-checks).
3. File a request with the DevOps team (via Jira or Slack) to make any resulting images [public](https://docs.github.com/en/packages/learn-github-packages/configuring-a-packages-access-control-and-visibility#configuring-access-to-container-images-for-an-organization).

---
**|| Previous: [New Repository](new-repository.md) || [Home](README.md) || Next: [Enable Branch Rules](enable-branch-rules.md) ||**
