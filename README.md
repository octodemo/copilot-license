# Copilot License Management

This project is an example of how to manage Copilot licenses using GitHub Actions.

## Issue Templates

The project uses an issue templates defined in [request-license.yml](../../../../../c:/Users/auste/source/copilot-license/.github/ISSUE_TEMPLATE/request-license.yml).

`request-license.yml` is used to request a Copilot License. It requires the user to provide a reason for the request.

## Workflows

There are two workflows in this project: [request-license.yml](../../../../../c:/Users/auste/source/copilot-license/.github/workflows/request-license.yml) and [cleanup.yml](../../../../../c:/Users/auste/source/copilot-license/.github/workflows/cleanup.yml).

`request-license.yml` is triggered when an issue is opened. It adds the user who opened the issue to the Copilot license, adds a comment to the issue stating that the license was added, and then closes the issue.

`cleanup.yml` is a scheduled workflow that runs every day at midnight. It uses the `copilot-license-cleanup` action to clean up inactive Copilot licenses.
