# Budgets for usage-based billing

Under usage-based billing, budget controls at the user, cost center, and enterprise levels determine how Copilot usage is served, metered, or blocked.

Every Copilot license includes AI credits that are pooled across your enterprise. Budget controls let you govern how individual users draw from that pool, and cap any additional spending once it's exhausted. This article explains what each budget control does, how the system evaluates them, and what happens when a limit is reached.

## Understanding the four budget controls

You have four budget controls, each serving a different purpose. They work together, not as alternatives.

### User-level budget

The user-level budget (ULB) caps how many AI credits a single user can consume in a billing cycle—both from the shared pool and from additional (metered) usage. This is the only control that is active during both the pool phase and the metered phase. ULBs always enforce a hard stop; there is no option to allow usage to continue beyond the limit. A $0 USD budget blocks the user immediately.

There are two types:

* **Universal user-level budget:** A default budget applied to every Copilot-licensed user in your enterprise. This is your primary tool for ensuring fair access to the shared pool.
* **Individual user-level budget:** A budget set for a specific user, which overrides the universal default and takes precedence over it entirely. Use this for power users who need higher limits, or to restrict specific users to a lower amount.

### Cost center budget

A cost center budget caps metered charges for a defined group of users or an organization. It does not limit how much a team draws from the pool. It is only active after the shared pool is exhausted.

When a cost center's budget is exhausted, only users in that cost center are blocked. Other users and cost centers are unaffected.

### Enterprise budget

The enterprise budget caps total metered charges across your entire enterprise. Like cost center budgets, it is only active after the shared pool is exhausted.

> \[!IMPORTANT]
> The enterprise budget is not a total monthly budget. It only caps metered charges after the pool is exhausted. Your total maximum bill is your license fees plus the enterprise budget. For example, 400 Copilot Business licenses at $19 USD per month means $7,600 USD in license fees. A $5,000 USD enterprise budget means your maximum bill is $12,600 USD, not $5,000 USD.

### How the controls compare

| Control                      | What it caps                                              | When it's active        | Scope           | Hard stop?                                                   |
| ---------------------------- | --------------------------------------------------------- | ----------------------- | --------------- | ------------------------------------------------------------ |
| Universal user-level budget  | Each user's total AI credit consumption                   | Always (pool + metered) | Per user        | Always                                                       |
| Individual user-level budget | A specific user's total consumption (overrides universal) | Always (pool + metered) | Per user        | Always                                                       |
| Cost center budget           | A team's metered charges after pool exhaustion            | Metered phase only      | Per cost center | Only if "Stop usage when budget limit is reached" is enabled |
| Enterprise budget            | Total enterprise metered charges after pool exhaustion    | Metered phase only      | Enterprise-wide | Only if "Stop usage when budget limit is reached" is enabled |

Any budget set to $0 USD stops usage immediately for the users it applies to.

## How billing flows through budgets

When someone in your enterprise uses Copilot, the system checks budget controls in a specific order to decide whether the request is served, metered, or blocked.

> \[!NOTE]
> For additional (metered) usage to occur, the "AI credit paid usage" policy must be enabled in your enterprise or organization settings. If this policy is disabled, usage is blocked when the shared pool is exhausted, regardless of your budget configuration.

Each request for an AI credit-consuming feature goes through these checks:

1. **User-level budget check.** The system first checks whether the user has exceeded their user-level budget. If yes, the request is blocked immediately—user-level budgets are always a hard stop. If no (or no ULB is set), the request continues.
2. **Shared pool check.** Next, the system checks whether the shared pool has AI credits remaining. If yes, the request is served from the pool at no extra cost. If the pool is empty, the request moves to metered usage at $0.01 USD per AI credit.
3. **Cost center or enterprise check.** For metered usage, the system checks whether the user is assigned to a cost center.

   * **If the user is in a cost center:** The cost center's budget is checked. If budget remains, the cost center pays. If the budget is exhausted, the system checks whether "Stop usage when budget limit is reached" is enabled.
   * **If the user is not in a cost center:** The enterprise spending limit is checked. If the limit has not been reached, the enterprise pays. If the limit has been reached, the system checks whether "Stop usage when budget limit is reached" is enabled.

   In both cases, if "Stop usage when budget limit is reached" is on, the user is blocked. If it is off, charges continue to accrue without a cap.

> \[!IMPORTANT]
> "Stop usage when budget limit is reached" applies to enterprise spending limits and cost center budgets only, and is off by default. Without it, charges continue to accrue past the limit. Always enable it when creating a spending limit. User-level budgets always enforce a hard stop and do not have this setting.

## How user-level budgets and spending limits interact

User-level budgets and spending limits are independent controls that serve different purposes. User-level budgets control how much each person can consume. Spending limits control how much metered usage your organization will pay for.

If these are not aligned, users can get blocked unexpectedly. The system applies a "lowest remaining headroom wins" rule: whichever budget has the least capacity remaining blocks the user first, regardless of what other budgets still have available. For example, if a user has $5 USD remaining on their individual user-level budget but the enterprise budget only has $1 USD remaining, the enterprise budget blocks them—even though their personal budget isn't exhausted.

This means that if your user-level budgets collectively allow more consumption than the shared pool provides, the difference spills over into metered charges. If your enterprise budget is too low to cover that gap, users get blocked before they reach their individual limits.

When you raise user-level budgets, check that your spending limits can still cover the resulting gap.

## Cost center exclusion

By default, cost center usage counts against the enterprise budget. Cost center exclusion is useful when a specific team needs independent spending authority that isn't constrained by the enterprise-wide cap, for example, a research team with its own budget approval. When exclusion is enabled for a cost center, that team's metered charges are not counted against the enterprise budget and will not be blocked when the enterprise budget is reached. Their spending is capped only by their own cost center budget.

## What happens when a user is blocked

When a user reaches any budget limit, their access to Copilot features that consume AI credits is blocked. There is no automatic fallback to lower-cost models. Code completions and next edit suggestions continue to work; they are included in all plans and do not consume AI credits.

A blocked user remains blocked until one of the following happens:

* The next billing cycle begins and monthly consumption resets.
* An administrator increases the relevant budget.

## Next steps

* To set up budget controls for your enterprise, see [Getting started with budget controls](/en/copilot/tutorials/budgets/getting-started-with-budget-controls).
* To choose the right configuration for your organization's structure, including common scenarios and sizing advice, see [Optimizing your budget configuration](/en/copilot/tutorials/budgets/optimizing-your-budget-configuration).