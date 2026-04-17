# Using GitHub Copilot code review on GitHub

GitHub Copilot reviews your pull requests and suggests ready-to-apply changes, so you get fast, actionable feedback on every commit.

Copilot code review is also available for organization members without a Copilot license, when enabled by an enterprise administrator or organization owner. See [Copilot code review for organization members without a Copilot license](/en/copilot/concepts/agents/code-review#copilot-code-review-for-organization-members-without-a-copilot-license).

## Request a review from Copilot

1. On GitHub.com, create or open a pull request.

2. Open the **Reviewers** menu, then select **Copilot**.

   ![Screenshot of selecting 'Copilot' from the 'Reviewers' menu.](/assets/images/help/copilot/code-review/request-review@2x.png)

3. Wait for Copilot to finish reviewing. This usually takes less than 30 seconds.

4. Read through Copilot's comments on the pull request.

   ![Screenshot of a code review left by Copilot.](/assets/images/help/copilot/code-review/review-comment@2x.png)

Copilot always leaves a "Comment" review, not an "Approve" or "Request changes" review. Its reviews do not count toward required approvals and will not block merging.

Copilot's review comments work like comments from human reviewers. Add reactions, reply, resolve, or hide them. Any replies you add are visible to other people but not to Copilot.

## Work with suggested changes

Copilot's feedback often includes suggested changes you can apply in a few clicks. Accept a single suggestion or group multiple suggestions into one commit. For more information, see [Incorporating feedback in your pull request](/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request).

To have Copilot cloud agent implement suggested changes directly:

1. Opt into the public preview for tools in Copilot code review and enable Copilot cloud agent.
2. On a review comment from GitHub Copilot code review, click **Implement suggestion**. This creates a draft comment where you instruct Copilot to address specific feedback. Copilot then creates a new pull request against your branch with the suggestions applied.

## Provide feedback on reviews

Rate Copilot's comments to help improve future suggestions.

1. On a review comment from Copilot, click the thumbs up (:+1:) or thumbs down (:-1:) button.

   ![Screenshot showing a Copilot code review comment with the thumbs up and thumbs down buttons.](/assets/images/help/copilot/code-review/feedback-controls@2x.png)

2. If you click thumbs down, optionally pick a reason and leave a comment, then click **Submit feedback**.

   ![Screenshot of the form for providing additional information when you give negative feedback on a comment from Copilot.](/assets/images/help/copilot/code-review/feedback-modal@2x.png)

## Request a re-review

Copilot does not automatically re-review when you push new changes. To request a re-review, click the <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-sync" aria-label="Re-request review" role="img"><path d="M1.705 8.005a.75.75 0 0 1 .834.656 5.5 5.5 0 0 0 9.592 2.97l-1.204-1.204a.25.25 0 0 1 .177-.427h3.646a.25.25 0 0 1 .25.25v3.646a.25.25 0 0 1-.427.177l-1.38-1.38A7.002 7.002 0 0 1 1.05 8.84a.75.75 0 0 1 .656-.834ZM8 2.5a5.487 5.487 0 0 0-4.131 1.869l1.204 1.204A.25.25 0 0 1 4.896 6H1.25A.25.25 0 0 1 1 5.75V2.104a.25.25 0 0 1 .427-.177l1.38 1.38A7.002 7.002 0 0 1 14.95 7.16a.75.75 0 0 1-1.49.178A5.5 5.5 0 0 0 8 2.5Z"></path></svg> button next to Copilot's name in the **Reviewers** menu.

When re-reviewing, Copilot may repeat previous comments, even if you resolved or downvoted them.

## Enable automatic reviews

By default, you request reviews from Copilot manually on each pull request. To enable automatic reviews for all pull requests, see [Configuring automatic code review by GitHub Copilot](/en/copilot/how-tos/agents/copilot-code-review/automatic-code-review).

## Customize reviews with custom instructions

You can customize Copilot code review by adding custom instructions to your repository.

Repository custom instructions can either be repository wide or path specific. You specify repository-wide custom instructions in a `.github/copilot-instructions.md` file in your repository. You can use this file to store information that you want Copilot to consider when reviewing code anywhere in the repository.

You can also write instructions that Copilot will only use when reviewing code in files that match a specified path. You write these instructions in one or more `.github/instructions/**/*.instructions.md` files.

For more information, see [Adding repository custom instructions for GitHub Copilot](/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot).

> \[!NOTE]
>
> * Copilot code review only reads the first 4,000 characters of any custom instruction file. Any instructions beyond this limit will not affect the reviews generated by Copilot code review. This limit does not apply to Copilot Chat or Copilot cloud agent.
> * When reviewing a pull request, Copilot uses the custom instructions in the base branch of the pull request. For example, if your pull request seeks to merge `my-feature-branch` into `main`, Copilot will use the custom instructions in `main`.

### Example

This example of a `.github/copilot-instructions.md` file contains three instructions that will be applied to all Copilot code reviews in the repository.

```text
When performing a code review, respond in Spanish.

When performing a code review, apply the checks in the `/security/security-checklist.md` file.

When performing a code review, focus on readability and avoid nested ternary operators.
```

## Further reading

* [About GitHub Copilot code review](/en/copilot/concepts/code-review)
* [Review output from Copilot](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/review-copilot-output)