# Getting started with the GitHub Copilot app

Sign in to the GitHub Copilot app, ask your first question in a quick chat, and then create a full agent session to make changes to your code.

> \[!NOTE] The GitHub Copilot app is in technical preview and subject to change.
>
> * **Copilot Business and Copilot Enterprise users** — Download and install from the [GitHub Copilot app repository](https://gh.io/github-copilot-app-repo?utm_source=docs-github-copilot-app-getting-started\&utm_medium=docs\&utm_campaign=github-copilot-app-tech-preview-2026) if your organization or enterprise has enabled preview features and Copilot CLI.
> * **Copilot Pro and Copilot Pro+ users** — To request access, [join the waitlist](https://gh.io/github-copilot-app?utm_source=docs-github-copilot-app-getting-started\&utm_medium=docs\&utm_campaign=github-copilot-app-tech-preview-2026).

## Prerequisites

* Access to the GitHub Copilot app. The app is currently in technical preview.
  * **Copilot Business or Copilot Enterprise users**: You have access, as long as your organization or enterprise has enabled preview features and enabled Copilot CLI. No waitlist is required, so you can download the app directly from the [GitHub Copilot app repository](https://gh.io/github-copilot-app-repo?utm_source=docs-github-copilot-app\&utm_medium=docs\&utm_campaign=github-copilot-app-tech-preview-2026).
  * **Copilot Pro or Copilot Pro+ users**: You must join the [waitlist](https://gh.io/github-copilot-app?utm_source=docs-github-copilot-app\&utm_medium=docs\&utm_campaign=github-copilot-app-tech-preview-2026) and be accepted into the preview to get access. Once accepted, you'll receive a link to download the app.
* The GitHub Copilot app installed on macOS, Windows, or Linux. Once you have access, you can download and install the application from the [GitHub Copilot app repository](https://gh.io/github-copilot-app-repo?utm_source=docs-github-copilot-app\&utm_medium=docs\&utm_campaign=github-copilot-app-tech-preview-2026).

## Opening the GitHub Copilot app for the first time

1. Open the GitHub Copilot app.
2. Click **Sign in to GitHub** and follow the prompts to authenticate.
3. The app walks you through onboarding. When prompted, select one or more repositories based on your recent GitHub activity, or choose a sample project. You can also skip this step and add repositories later.
4. Choose a theme, then complete onboarding.

## Connecting a repository

To work on code, you need at least one repository connected to the app. If you skipped repository setup during onboarding, or want to add more repositories later:

1. Click the **+** button in the sidebar next to "Sessions".
2. Under **Add project from**, choose one of the following:
   * **Local folder or repository** — Select a folder already on your machine.
   * **GitHub repository** — Browse and clone a repository from GitHub.
   * **Repository URL** — Clone from any Git URL.

## Orienting yourself

The sidebar gives you access to the main areas of the app:

* **Inbox** - Browse and filter issues and pull requests from your repositories, check CI status, and leave reviews.
* **Workflows** — Saved agent tasks that run on a schedule or on demand.
* **Search** — Search across your repositories directly from the app.
* **Sessions** — Active agent sessions, grouped by repository. This also includes **Quick chats**, which are general chat conversations.

## Starting a quick chat

The fastest way to try the GitHub Copilot app is with a quick chat. Quick chats let you ask questions and brainstorm without creating a branch or worktree.

1. In the sidebar, click **+** next to "Quick chats" to open a new chat.
2. Type a question or prompt—for example, "Give me an overview of the octocat repository."
3. The agent responds in the conversation view. You can continue the conversation, ask follow-up questions, or start a new chat.

## Creating your first session

When you are ready to make changes to code, create a session. You can start from an issue or describe a task directly.

### Starting from an issue

1. Click **Inbox** in the sidebar.
2. Browse or filter to find an issue, then click it to view its details.
3. Click **Start a session**. The app creates a new session with the issue context already loaded and automatically uses **Plan** mode.
4. The agent proposes a plan. Review the plan, then you can choose to let the agent start working on a pull request or have it propose changes that you can then manually apply.
5. If you've told it to, the agent creates a branch, makes changes, and even creates a pull request that you can then review and iterate on.

### Starting from a task

If you do not have an issue to work from, you can describe a task directly.

1. In the sidebar, click **+** to start a new session and select a repository.
2. Select a session mode from the dropdown above the prompt field—for example, **Interactive** to work collaboratively with the agent.
3. Describe a task—for example, "Fix the failing test in `utils.test.ts`" or "Add input validation to the signup form."
4. The agent will make changes based on your direction. Follow along in the conversation view and provide feedback to steer the agent.

## Next steps

Find out more about using the GitHub Copilot app:

* [Working with agent sessions in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/agent-sessions)
* [Managing issues and pull requests with the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/managing-issues-and-pull-requests)
* [Using scheduled workflows in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/using-scheduled-workflows)