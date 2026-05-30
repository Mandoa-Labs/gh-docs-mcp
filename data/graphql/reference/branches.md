# Branches

Reference documentation for GraphQL schema types in the Branches category.

## BranchActorAllowanceActor - union

Types which can be actors for BranchActorAllowance objects.

### Possible types for `BranchActorAllowanceActor`

* App
* Team
* User

## BranchNamePatternParameters - object

Parameters to be used for the branch_name_pattern rule.

### Fields for `BranchNamePatternParameters`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean!): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## BranchNamePatternParametersInput - input object

Parameters to be used for the branch_name_pattern rule.

### Input fields for `BranchNamePatternParametersInput`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## BranchProtectionRule - object

A branch protection rule.

**Implements:** Node

### Fields for `BranchProtectionRule`

* `allowsDeletions` (Boolean!): Can this branch be deleted.
* `allowsForcePushes` (Boolean!): Are force pushes allowed on this branch.
* `blocksCreations` (Boolean!): Is branch creation a protected operation.
* `branchProtectionRuleConflicts` (BranchProtectionRuleConflictConnection!): A list of conflicts matching branches protection rule and other branch protection rules. _(Pagination: `after`, `before`, `first`, `last`)_
* `bypassForcePushAllowances` (BypassForcePushAllowanceConnection!): A list of actors able to force push for this branch protection rule. _(Pagination: `after`, `before`, `first`, `last`)_
* `bypassPullRequestAllowances` (BypassPullRequestAllowanceConnection!): A list of actors able to bypass PRs for this branch protection rule. _(Pagination: `after`, `before`, `first`, `last`)_
* `creator` (Actor): The actor who created this branch protection rule.
* `databaseId` (Int): Identifies the primary key from the database.
* `dismissesStaleReviews` (Boolean!): Will new commits pushed to matching branches dismiss pull request review approvals.
* `id` (ID!): The Node ID of the BranchProtectionRule object.
* `isAdminEnforced` (Boolean!): Can admins override branch protection.
* `lockAllowsFetchAndMerge` (Boolean!): Whether users can pull changes from upstream when the branch is locked. Set to
true to allow fork syncing. Set to false to prevent fork syncing.
* `lockBranch` (Boolean!): Whether to set the branch as read-only. If this is true, users will not be able to push to the branch.
* `matchingRefs` (RefConnection!): Repository refs that are protected by this rule.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `query` (String): Filters refs with query on name.

* `pattern` (String!): Identifies the protection rule pattern.
* `pushAllowances` (PushAllowanceConnection!): A list push allowances for this branch protection rule. _(Pagination: `after`, `before`, `first`, `last`)_
* `repository` (Repository): The repository associated with this branch protection rule.
* `requireLastPushApproval` (Boolean!): Whether the most recent push must be approved by someone other than the person who pushed it.
* `requiredApprovingReviewCount` (Int): Number of approving reviews required to update matching branches.
* `requiredDeploymentEnvironments` ([String]): List of required deployment environments that must be deployed successfully to update matching branches.
* `requiredStatusCheckContexts` ([String]): List of required status check contexts that must pass for commits to be accepted to matching branches.
* `requiredStatusChecks` ([RequiredStatusCheckDescription!]): List of required status checks that must pass for commits to be accepted to matching branches.
* `requiresApprovingReviews` (Boolean!): Are approving reviews required to update matching branches.
* `requiresCodeOwnerReviews` (Boolean!): Are reviews from code owners required to update matching branches.
* `requiresCommitSignatures` (Boolean!): Are commits required to be signed.
* `requiresConversationResolution` (Boolean!): Are conversations required to be resolved before merging.
* `requiresDeployments` (Boolean!): Does this branch require deployment to specific environments before merging.
* `requiresLinearHistory` (Boolean!): Are merge commits prohibited from being pushed to this branch.
* `requiresStatusChecks` (Boolean!): Are status checks required to update matching branches.
* `requiresStrictStatusChecks` (Boolean!): Are branches required to be up to date before merging.
* `restrictsPushes` (Boolean!): Is pushing to matching branches restricted.
* `restrictsReviewDismissals` (Boolean!): Is dismissal of pull request reviews restricted.
* `reviewDismissalAllowances` (ReviewDismissalAllowanceConnection!): A list review dismissal allowances for this branch protection rule. _(Pagination: `after`, `before`, `first`, `last`)_

## BranchProtectionRuleConflict - object

A conflict between two branch protection rules.

### Fields for `BranchProtectionRuleConflict`

* `branchProtectionRule` (BranchProtectionRule): Identifies the branch protection rule.
* `conflictingBranchProtectionRule` (BranchProtectionRule): Identifies the conflicting branch protection rule.
* `ref` (Ref): Identifies the branch ref that has conflicting rules.

## BranchProtectionRuleConflictConnection - object

The connection type for BranchProtectionRuleConflict.

### Fields for `BranchProtectionRuleConflictConnection`

* `edges` ([BranchProtectionRuleConflictEdge]): A list of edges.
* `nodes` ([BranchProtectionRuleConflict]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## BranchProtectionRuleConflictEdge - object

An edge in a connection.

### Fields for `BranchProtectionRuleConflictEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (BranchProtectionRuleConflict): The item at the end of the edge.

## BranchProtectionRuleConnection - object

The connection type for BranchProtectionRule.

### Fields for `BranchProtectionRuleConnection`

* `edges` ([BranchProtectionRuleEdge]): A list of edges.
* `nodes` ([BranchProtectionRule]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## BranchProtectionRuleEdge - object

An edge in a connection.

### Fields for `BranchProtectionRuleEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (BranchProtectionRule): The item at the end of the edge.

## BypassForcePushAllowance - object

A user, team, or app who has the ability to bypass a force push requirement on a protected branch.

**Implements:** Node

### Fields for `BypassForcePushAllowance`

* `actor` (BranchActorAllowanceActor): The actor that can force push.
* `branchProtectionRule` (BranchProtectionRule): Identifies the branch protection rule associated with the allowed user, team, or app.
* `id` (ID!): The Node ID of the BypassForcePushAllowance object.

## BypassForcePushAllowanceConnection - object

The connection type for BypassForcePushAllowance.

### Fields for `BypassForcePushAllowanceConnection`

* `edges` ([BypassForcePushAllowanceEdge]): A list of edges.
* `nodes` ([BypassForcePushAllowance]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## BypassForcePushAllowanceEdge - object

An edge in a connection.

### Fields for `BypassForcePushAllowanceEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (BypassForcePushAllowance): The item at the end of the edge.

## BypassPullRequestAllowance - object

A user, team, or app who has the ability to bypass a pull request requirement on a protected branch.

**Implements:** Node

### Fields for `BypassPullRequestAllowance`

* `actor` (BranchActorAllowanceActor): The actor that can bypass.
* `branchProtectionRule` (BranchProtectionRule): Identifies the branch protection rule associated with the allowed user, team, or app.
* `id` (ID!): The Node ID of the BypassPullRequestAllowance object.

## BypassPullRequestAllowanceConnection - object

The connection type for BypassPullRequestAllowance.

### Fields for `BypassPullRequestAllowanceConnection`

* `edges` ([BypassPullRequestAllowanceEdge]): A list of edges.
* `nodes` ([BypassPullRequestAllowance]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## BypassPullRequestAllowanceEdge - object

An edge in a connection.

### Fields for `BypassPullRequestAllowanceEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (BypassPullRequestAllowance): The item at the end of the edge.

## createBranchProtectionRule - mutation

Create a new branch protection rule.

### Input fields for `createBranchProtectionRule`

* `input` (CreateBranchProtectionRuleInput!): 

### Return fields for `createBranchProtectionRule`

* `branchProtectionRule` (BranchProtectionRule): The newly created BranchProtectionRule.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## CreateBranchProtectionRuleInput - input object

Autogenerated input type of CreateBranchProtectionRule.

### Input fields for `CreateBranchProtectionRuleInput`

* `allowsDeletions` (Boolean): Can this branch be deleted.
* `allowsForcePushes` (Boolean): Are force pushes allowed on this branch.
* `blocksCreations` (Boolean): Is branch creation a protected operation.
* `bypassForcePushActorIds` ([ID!]): A list of User, Team, or App IDs allowed to bypass force push targeting matching branches.
* `bypassPullRequestActorIds` ([ID!]): A list of User, Team, or App IDs allowed to bypass pull requests targeting matching branches.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `dismissesStaleReviews` (Boolean): Will new commits pushed to matching branches dismiss pull request review approvals.
* `isAdminEnforced` (Boolean): Can admins override branch protection.
* `lockAllowsFetchAndMerge` (Boolean): Whether users can pull changes from upstream when the branch is locked. Set to
true to allow fork syncing. Set to false to prevent fork syncing.
* `lockBranch` (Boolean): Whether to set the branch as read-only. If this is true, users will not be able to push to the branch.
* `pattern` (String!): The glob-like pattern used to determine matching branches.
* `pushActorIds` ([ID!]): A list of User, Team, or App IDs allowed to push to matching branches.
* `repositoryId` (ID!): The global relay id of the repository in which a new branch protection rule should be created in.
* `requireLastPushApproval` (Boolean): Whether the most recent push must be approved by someone other than the person who pushed it.
* `requiredApprovingReviewCount` (Int): Number of approving reviews required to update matching branches.
* `requiredDeploymentEnvironments` ([String!]): The list of required deployment environments.
* `requiredStatusCheckContexts` ([String!]): List of required status check contexts that must pass for commits to be accepted to matching branches.
* `requiredStatusChecks` ([RequiredStatusCheckInput!]): The list of required status checks.
* `requiresApprovingReviews` (Boolean): Are approving reviews required to update matching branches.
* `requiresCodeOwnerReviews` (Boolean): Are reviews from code owners required to update matching branches.
* `requiresCommitSignatures` (Boolean): Are commits required to be signed.
* `requiresConversationResolution` (Boolean): Are conversations required to be resolved before merging.
* `requiresDeployments` (Boolean): Are successful deployments required before merging.
* `requiresLinearHistory` (Boolean): Are merge commits prohibited from being pushed to this branch.
* `requiresStatusChecks` (Boolean): Are status checks required to update matching branches.
* `requiresStrictStatusChecks` (Boolean): Are branches required to be up to date before merging.
* `restrictsPushes` (Boolean): Is pushing to matching branches restricted.
* `restrictsReviewDismissals` (Boolean): Is dismissal of pull request reviews restricted.
* `reviewDismissalActorIds` ([ID!]): A list of User, Team, or App IDs allowed to dismiss reviews on pull requests targeting matching branches.

## deleteBranchProtectionRule - mutation

Delete a branch protection rule.

### Input fields for `deleteBranchProtectionRule`

* `input` (DeleteBranchProtectionRuleInput!): 

### Return fields for `deleteBranchProtectionRule`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## DeleteBranchProtectionRuleInput - input object

Autogenerated input type of DeleteBranchProtectionRule.

### Input fields for `DeleteBranchProtectionRuleInput`

* `branchProtectionRuleId` (ID!): The global relay id of the branch protection rule to be deleted.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## mergeBranch - mutation

Merge a head into a branch.

### Input fields for `mergeBranch`

* `input` (MergeBranchInput!): 

### Return fields for `mergeBranch`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `mergeCommit` (Commit): The resulting merge Commit.

## MergeBranchInput - input object

Autogenerated input type of MergeBranch.

### Input fields for `MergeBranchInput`

* `authorEmail` (String): The email address to associate with this commit.
* `base` (String!): The name of the base branch that the provided head will be merged into.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `commitMessage` (String): Message to use for the merge commit. If omitted, a default will be used.
* `head` (String!): The head to merge into the base branch. This can be a branch name or a commit GitObjectID.
* `repositoryId` (ID!): The Node ID of the Repository containing the base branch that will be modified.

## PushAllowance - object

A team, user, or app who has the ability to push to a protected branch.

**Implements:** Node

### Fields for `PushAllowance`

* `actor` (PushAllowanceActor): The actor that can push.
* `branchProtectionRule` (BranchProtectionRule): Identifies the branch protection rule associated with the allowed user, team, or app.
* `id` (ID!): The Node ID of the PushAllowance object.

## PushAllowanceActor - union

Types that can be an actor.

### Possible types for `PushAllowanceActor`

* App
* Team
* User

## PushAllowanceConnection - object

The connection type for PushAllowance.

### Fields for `PushAllowanceConnection`

* `edges` ([PushAllowanceEdge]): A list of edges.
* `nodes` ([PushAllowance]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## PushAllowanceEdge - object

An edge in a connection.

### Fields for `PushAllowanceEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (PushAllowance): The item at the end of the edge.

## RefNameConditionTarget - object

Parameters to be used for the ref_name condition.

### Fields for `RefNameConditionTarget`

* `exclude` ([String!]!): Array of ref names or patterns to exclude. The condition will not pass if any of these patterns match.
* `include` ([String!]!): Array of ref names or patterns to include. One of these patterns must match
for the condition to pass. Also accepts ~DEFAULT_BRANCH to include the
default branch or ~ALL to include all branches.

## RefNameConditionTargetInput - input object

Parameters to be used for the ref_name condition.

### Input fields for `RefNameConditionTargetInput`

* `exclude` ([String!]!): Array of ref names or patterns to exclude. The condition will not pass if any of these patterns match.
* `include` ([String!]!): Array of ref names or patterns to include. One of these patterns must match
for the condition to pass. Also accepts ~DEFAULT_BRANCH to include the
default branch or ~ALL to include all branches.

## RequiredStatusCheckDescription - object

Represents a required status check for a protected branch, but not any specific run of that check.

### Fields for `RequiredStatusCheckDescription`

* `app` (App): The App that must provide this status in order for it to be accepted.
* `context` (String!): The name of this status.

## RequiredStatusCheckInput - input object

Specifies the attributes for a new or updated required status check.

### Input fields for `RequiredStatusCheckInput`

* `appId` (ID): The ID of the App that must set the status in order for it to be accepted.
Omit this value to use whichever app has recently been setting this status, or
use "any" to allow any app to set the status.
* `context` (String!): Status check context that must pass for commits to be accepted to the matching branch.

## RequiredStatusChecksParameters - object

Choose which status checks must pass before the ref is updated. When enabled,
commits must first be pushed to another ref where the checks pass.

### Fields for `RequiredStatusChecksParameters`

* `doNotEnforceOnCreate` (Boolean!): Allow repositories and branches to be created if a check would otherwise prohibit it.
* `requiredStatusChecks` ([StatusCheckConfiguration!]!): Status checks that are required.
* `strictRequiredStatusChecksPolicy` (Boolean!): Whether pull requests targeting a matching branch must be tested with the
latest code. This setting will not take effect unless at least one status
check is enabled.

## RequiredStatusChecksParametersInput - input object

Choose which status checks must pass before the ref is updated. When enabled,
commits must first be pushed to another ref where the checks pass.

### Input fields for `RequiredStatusChecksParametersInput`

* `doNotEnforceOnCreate` (Boolean): Allow repositories and branches to be created if a check would otherwise prohibit it.
* `requiredStatusChecks` ([StatusCheckConfigurationInput!]!): Status checks that are required.
* `strictRequiredStatusChecksPolicy` (Boolean!): Whether pull requests targeting a matching branch must be tested with the
latest code. This setting will not take effect unless at least one status
check is enabled.

## ReviewDismissalAllowance - object

A user, team, or app who has the ability to dismiss a review on a protected branch.

**Implements:** Node

### Fields for `ReviewDismissalAllowance`

* `actor` (ReviewDismissalAllowanceActor): The actor that can dismiss.
* `branchProtectionRule` (BranchProtectionRule): Identifies the branch protection rule associated with the allowed user, team, or app.
* `id` (ID!): The Node ID of the ReviewDismissalAllowance object.

## ReviewDismissalAllowanceActor - union

Types that can be an actor.

### Possible types for `ReviewDismissalAllowanceActor`

* App
* Team
* User

## ReviewDismissalAllowanceConnection - object

The connection type for ReviewDismissalAllowance.

### Fields for `ReviewDismissalAllowanceConnection`

* `edges` ([ReviewDismissalAllowanceEdge]): A list of edges.
* `nodes` ([ReviewDismissalAllowance]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## ReviewDismissalAllowanceEdge - object

An edge in a connection.

### Fields for `ReviewDismissalAllowanceEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (ReviewDismissalAllowance): The item at the end of the edge.

## updateBranchProtectionRule - mutation

Update a branch protection rule.

### Input fields for `updateBranchProtectionRule`

* `input` (UpdateBranchProtectionRuleInput!): 

### Return fields for `updateBranchProtectionRule`

* `branchProtectionRule` (BranchProtectionRule): The newly created BranchProtectionRule.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## UpdateBranchProtectionRuleInput - input object

Autogenerated input type of UpdateBranchProtectionRule.

### Input fields for `UpdateBranchProtectionRuleInput`

* `allowsDeletions` (Boolean): Can this branch be deleted.
* `allowsForcePushes` (Boolean): Are force pushes allowed on this branch.
* `blocksCreations` (Boolean): Is branch creation a protected operation.
* `branchProtectionRuleId` (ID!): The global relay id of the branch protection rule to be updated.
* `bypassForcePushActorIds` ([ID!]): A list of User, Team, or App IDs allowed to bypass force push targeting matching branches.
* `bypassPullRequestActorIds` ([ID!]): A list of User, Team, or App IDs allowed to bypass pull requests targeting matching branches.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `dismissesStaleReviews` (Boolean): Will new commits pushed to matching branches dismiss pull request review approvals.
* `isAdminEnforced` (Boolean): Can admins override branch protection.
* `lockAllowsFetchAndMerge` (Boolean): Whether users can pull changes from upstream when the branch is locked. Set to
true to allow fork syncing. Set to false to prevent fork syncing.
* `lockBranch` (Boolean): Whether to set the branch as read-only. If this is true, users will not be able to push to the branch.
* `pattern` (String): The glob-like pattern used to determine matching branches.
* `pushActorIds` ([ID!]): A list of User, Team, or App IDs allowed to push to matching branches.
* `requireLastPushApproval` (Boolean): Whether the most recent push must be approved by someone other than the person who pushed it.
* `requiredApprovingReviewCount` (Int): Number of approving reviews required to update matching branches.
* `requiredDeploymentEnvironments` ([String!]): The list of required deployment environments.
* `requiredStatusCheckContexts` ([String!]): List of required status check contexts that must pass for commits to be accepted to matching branches.
* `requiredStatusChecks` ([RequiredStatusCheckInput!]): The list of required status checks.
* `requiresApprovingReviews` (Boolean): Are approving reviews required to update matching branches.
* `requiresCodeOwnerReviews` (Boolean): Are reviews from code owners required to update matching branches.
* `requiresCommitSignatures` (Boolean): Are commits required to be signed.
* `requiresConversationResolution` (Boolean): Are conversations required to be resolved before merging.
* `requiresDeployments` (Boolean): Are successful deployments required before merging.
* `requiresLinearHistory` (Boolean): Are merge commits prohibited from being pushed to this branch.
* `requiresStatusChecks` (Boolean): Are status checks required to update matching branches.
* `requiresStrictStatusChecks` (Boolean): Are branches required to be up to date before merging.
* `restrictsPushes` (Boolean): Is pushing to matching branches restricted.
* `restrictsReviewDismissals` (Boolean): Is dismissal of pull request reviews restricted.
* `reviewDismissalActorIds` ([ID!]): A list of User, Team, or App IDs allowed to dismiss reviews on pull requests targeting matching branches.