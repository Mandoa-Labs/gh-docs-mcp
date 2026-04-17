# Get started with Copilot agents on GitHub

Try Copilot cloud agent end-to-end in about ten minutes.

## Prerequisite

You need a repository where Copilot cloud agent is enabled. For Copilot Business and Copilot Enterprise subscribers, an administrator must enable the agent before you can use it. See [Managing access to GitHub Copilot cloud agent](/en/copilot/concepts/agents/cloud-agent/access-management).

## Step 1: Assign an issue to Copilot

Pick a repository where Copilot cloud agent is enabled and find an open issue—or create a small one, such as "Add a CONTRIBUTING.md file."

1. In the right sidebar, click **Assignees**, then select **Copilot**.
2. Optionally, add instructions in the **Optional prompt** field.

   For example: `Keep the file short and include a code of conduct section.`
3. Click **Assign**.

Copilot starts a session and begins working on a pull request.

## Step 2: Start a research task at the same time

While Copilot works on the issue, start a second, non-coding task to see two sessions running in parallel.

1. In the same repository, click the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-agent" aria-label="agent" role="img"><path d="M14.5 8.9v-.052A2.956 2.956 0 0 0 11.542 5.9a.815.815 0 0 1-.751-.501l-.145-.348A3.496 3.496 0 0 0 7.421 2.9h-.206a3.754 3.754 0 0 0-3.736 4.118l.011.121a.822.822 0 0 1-.619.879A1.81 1.81 0 0 0 1.5 9.773v.14c0 1.097.89 1.987 1.987 1.987H4.5a.75.75 0 0 1 0 1.5H3.487A3.487 3.487 0 0 1 0 9.913v-.14C0 8.449.785 7.274 1.963 6.75A5.253 5.253 0 0 1 7.215 1.4h.206a4.992 4.992 0 0 1 4.586 3.024A4.455 4.455 0 0 1 16 8.848V8.9a.75.75 0 0 1-1.5 0Z"></path><path d="m8.38 7.67 2.25 2.25a.749.749 0 0 1 0 1.061L8.38 13.23a.749.749 0 1 1-1.06-1.06l1.719-1.72L7.32 8.731A.75.75 0 0 1 8.38 7.67ZM15 13.45h-3a.75.75 0 0 1 0-1.5h3a.75.75 0 0 1 0 1.5Z"></path></svg> Agents** tab.
2. Type a research prompt.

   For example: `Investigate which dependencies in this repo are outdated and summarize what upgrading would involve.`
3. Click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-paper-airplane" aria-label="Start task" role="img"><path d="M.989 8 .064 2.68a1.342 1.342 0 0 1 1.85-1.462l13.402 5.744a1.13 1.13 0 0 1 0 2.076L1.913 14.782a1.343 1.343 0 0 1-1.85-1.463L.99 8Zm.603-5.288L2.38 7.25h4.87a.75.75 0 0 1 0 1.5H2.38l-.788 4.538L13.929 8Z"></path></svg>** or press <kbd>Enter</kbd>.

A second session appears in the panel alongside the first.

## Step 3: Watch both sessions

Both sessions update in real time. Click either session to view the agent's reasoning, the files it reads, and the changes it makes.

While a session is running, type in the prompt box below the log to steer the agent.

For example: `Focus on security-related dependencies first.`

For more details on monitoring, steering, and stopping sessions, see [Manage and track Copilot cloud agent sessions](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/manage-and-track-agents).

## Step 4: Request a Copilot code review on the pull request

When the coding task finishes, Copilot opens a pull request and adds you as a reviewer.

1. Open the pull request from the notification or from the session log.
2. In the right sidebar, click **Reviewers**, then select **Copilot**.
3. Wait for Copilot code review to leave comments—usually under 30 seconds.

Read through the review comments. Copilot may suggest changes you can apply directly with a click.

For the full set of code-review options, see [Using GitHub Copilot code review on GitHub](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review).

## Step 5: Review the output and iterate

Now review the code changes yourself, just as you would for any contributor's pull request.

* **Request changes from Copilot** — mention `@copilot` in a comment describing what to fix. Copilot pushes new commits to the same branch.
* **Make changes yourself** — check out the branch and push your own commits.
* **Approve and merge** — when you're satisfied, merge the pull request.

For more on reviewing Copilot's work, see [Review output from Copilot](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/review-copilot-output).

## Next steps

* [Best practices for using GitHub Copilot to work on tasks](/en/copilot/tutorials/cloud-agent/get-the-best-results) — Write effective prompts and get the most out of agents.