# Managing issues and pull requests with the GitHub Copilot app

Pick up an issue, direct an agent to implement changes, and land a pull request—all without leaving the GitHub Copilot app.

> [!NOTE] The GitHub Copilot app is in technical preview and subject to change.
>
> * **Copilot Business and Copilot Enterprise users** — Download and install from the [GitHub Copilot app repository](https://gh.io/github-copilot-app-repo?utm_source=docs-github-copilot-app-managing-issues-prs&utm_medium=docs&utm_campaign=github-copilot-app-tech-preview-2026) if your organization or enterprise has enabled preview features and Copilot CLI.
> * **Copilot Pro and Copilot Pro+ users** — To request access, [join the waitlist](https://gh.io/github-copilot-app?utm_source=docs-github-copilot-app-managing-issues-prs&utm_medium=docs&utm_campaign=github-copilot-app-tech-preview-2026).

## Browsing your inbox

Click **Inbox** in the sidebar to see your issues and pull requests in one place. The inbox is organized into sections—by default, **All**, **Active**, **Review requests**, and **Done**. You can edit the default sections or add new ones with your own filters. Use the search bar within any section to find items by keyword or qualifiers like `label:bug`.

## Starting a session from an issue

1. In the **Inbox**, find the issue you want to work on, then click it to view its details.
1. Click **Start a session**. The app creates a new session with the issue context already loaded and automatically selects **Plan** mode.
1. The agent proposes a plan. Review the plan, then let the agent start working or have it propose changes that you can apply manually.
1. Once you approve, the agent creates a branch, implements the changes, and opens a pull request for you to review.

## Reviewing a pull request

1. Click a pull request in the **Inbox** to see its overview—including the summary, CI check results, and review activity.
1. Switch to the **Files changed** tab to review the diff.
1. Click **Create session** to start a session for the pull request. Within the session, you can leave review comments on the diff, or ask the agent to make changes.
1. Once done reviewing in the session, you can go back to the pull request detail view and click **Review** at the top to submit a review.

You can also open the pull request in your browser or in another IDE directly from the app.

## Responding to a review

You can respond to review comments and resolve failing CI checks in the GitHub Copilot app.

1. Open a pull request.
1. Scroll down the page to see review comments on your PR. To ask an agent to resolve a comment, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="The Copilot icon" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Fix**.
1. At the bottom of the page, view the status of CI checks. To ask an agent to fix failing checks, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="The Copilot icon" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Fix failing checks**.

## Merging a pull request

When you want to merge a pull request, you can enable **agent merge** at the top of the app. Agent merge will prompt the workspace's Copilot session to read your pull request, fix what is blocking it, and merge it as soon as GitHub allows. It runs in the background, survives app restarts, and turns itself off once your pull request is merged.