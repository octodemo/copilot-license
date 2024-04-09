# How to use this

1. Fork this repository into your organization.
1. [Register a GitHub App](https://docs.github.com/en/enterprise-cloud@latest/apps/creating-github-apps/registering-a-github-app/registering-a-github-app#registering-a-github-app) and [install it](https://docs.github.com/en/enterprise-cloud@latest/apps/using-github-apps/installing-your-own-github-app#installing-your-own-github-app) on your fork.
   1. Permissions needed:
      1. Issues: Read & write
      2. Copilot: Read & write
2. [Add actions secrets](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions#creating-secrets-for-a-repository)
   1. `APP_PRIVATE_KEY`: The private key of the GitHub App you created.
3. [Add actions variables](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository)
   1. `APP_ID`: The ID of the GitHub App you created.
4. Create an issue in your fork to request a license.

There are many things you can modify in this project. Most notably:
* The issue template in [request-license.yml](.github/ISSUE_TEMPLATE/request-license.yml).
* The cleanup schedule in [cleanup.yml](.github/workflows/cleanup.yml).

# Technical Details

## Issue Templates

The project uses an issue templates defined in [request-license.yml](.github/ISSUE_TEMPLATE/request-license.yml).

`request-license.yml` is used to request a Copilot License. It requires the user to provide a reason for the request.

## Workflows

There are two workflows in this project: [request-license.yml](.github/workflows/request-license.yml) and [cleanup.yml](.github/workflows/cleanup.yml).

`request-license.yml` is triggered when an issue is opened. It adds the user who opened the issue to the Copilot license, adds a comment to the issue stating that the license was added, and then closes the issue.

`cleanup.yml` is a scheduled workflow that runs every day at midnight. It uses the `copilot-license-cleanup` action to clean up inactive Copilot licenses.
