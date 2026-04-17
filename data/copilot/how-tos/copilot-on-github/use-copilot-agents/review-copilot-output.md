# Review output from Copilot

Copilot pull requests deserve the same thorough review as any contribution. Mention @copilot to request changes, or push commits directly to the branch.

## Review Copilot's changes

When Copilot finishes a coding task and requests your review, check the pull request thoroughly before merging.

> \[!IMPORTANT]
> If your repository requires pull request approvals, **your approval of a Copilot pull request won't count** toward the required number. Another reviewer must approve the pull request before it can be merged.

Mention `@copilot` in a pull request comment to request changes. By default, Copilot pushes commits directly to the pull request branch. To create a separate pull request instead, describe that in your comment. You can also check out the branch and push changes yourself.

Batch review comments instead of submitting them individually. When submitting a pull request comment (not a review or review comment) through the GitHub web interface, select a model with the model picker. Copilot uses the model from the original pull request by default.

Copilot only responds to comments from people who have write access to the repository.

When Copilot starts a new session in response to your comment, an eyes emoji (👀) reaction appears on the comment. A "Copilot has started work" event appears in the pull request timeline.

![Screenshot of a pull request timeline with a review comment with the eyes reaction and a "Copilot started work" timeline event.](/assets/images/help/copilot/cloud-agent/comment-to-agent-on-pr.png)

Copilot remembers context from previous sessions on the same pull request, so follow-up requests are faster and more reliable. If the pull request was created by a custom agent, mentioning `@copilot` continues using that same agent.

## Resolve merge conflicts

You can ask Copilot to resolve merge conflicts on a pull request in two ways:

* **Using the "Fix with Copilot" button**: If a pull request has merge conflicts, click the **Fix with Copilot** button that appears in the merge box.
* **Using an @copilot mention**: Mention `@copilot` in a comment on the pull request and ask it to fix the conflicts—for example, "@copilot resolve the merge conflicts on this PR."

Copilot analyzes the conflicting changes, resolves them, and verifies that the build, tests, and linter still pass. It then requests your review so you can confirm the resolution before merging.

## Manage GitHub Actions workflow runs

By default, GitHub Actions workflows will not run automatically when Copilot pushes changes to a pull request.

GitHub Actions workflows can be privileged and have access to sensitive secrets. Inspect the proposed changes in the pull request and ensure that you are comfortable running your workflows on the pull request branch. You should be especially alert to any proposed changes in the `.github/workflows/` directory that affect workflow files.

To allow GitHub Actions workflows to run, click the **Approve and run workflows** button in the pull request's merge box.

![Screenshot of the merge box on a pull request from Copilot with the "Approve and run workflows" button.](/assets/images/help/copilot/cloud-agent/approve-and-run-workflows.png)

Optionally, you can configure Copilot cloud agent to allow GitHub Actions workflows to run without human intervention. For more information, see [Configuring settings for GitHub Copilot cloud agent](/en/copilot/how-tos/use-copilot-agents/cloud-agent/configuring-agent-settings).

## Give feedback on Copilot's work

Use the feedback buttons on Copilot's pull requests and comments to rate the output. Your feedback helps improve Copilot's quality.

1. On a pull request or comment from Copilot, click the thumbs up (:+1:) or thumbs down (:-1:) button.
2. If you click the thumbs down button, optionally select a reason and leave a comment, then click **Submit feedback**.

## Further reading

* [Best practices for using GitHub Copilot to work on tasks](/en/copilot/tutorials/cloud-agent/get-the-best-results)
* [Troubleshooting GitHub Copilot cloud agent](/en/copilot/how-tos/use-copilot-agents/cloud-agent/troubleshoot-cloud-agent)