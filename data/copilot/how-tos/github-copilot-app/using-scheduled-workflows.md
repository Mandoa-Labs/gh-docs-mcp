# Using scheduled workflows in the GitHub Copilot app

Automate recurring agent tasks so they run on a schedule or on demand, without manual intervention.

> [!NOTE] The GitHub Copilot app is in technical preview and subject to change.
>
> * **Copilot Business and Copilot Enterprise users** — Download and install from the [GitHub Copilot app repository](https://gh.io/github-copilot-app-repo?utm_source=docs-github-copilot-app-scheduled-workflows&utm_medium=docs&utm_campaign=github-copilot-app-tech-preview-2026) if your organization or enterprise has enabled preview features and Copilot CLI.
> * **Copilot Pro and Copilot Pro+ users** — To request access, [join the waitlist](https://gh.io/github-copilot-app?utm_source=docs-github-copilot-app-scheduled-workflows&utm_medium=docs&utm_campaign=github-copilot-app-tech-preview-2026).

## About workflows

Workflows let you save recurring agent tasks and run them on a schedule or on demand. For example, you can create a workflow that triages new issues daily or checks your open pull requests for review status each morning.

Click **Workflows** in the sidebar to see your saved workflows. Each workflow shows its name, schedule, associated repository, and last run status.

## Creating a workflow

1. Click **New workflow** in the top-right corner.
1. Give the workflow a name and write a prompt describing the task. You can type `/` to add skills.
1. Set the interval—either a recurring schedule (for example, daily at 9:00 AM) or manual.
1. Optionally, configure the session mode, project, model, and reasoning effort.
1. Click **Create** to save, or select **Create and run** to save and test the workflow immediately.

## Running a workflow on demand

You can trigger any saved workflow manually by clicking the play button on its card on the "Workflows" page, without waiting for its next scheduled run.