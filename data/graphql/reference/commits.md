# Commits

Reference documentation for GraphQL schema types in the Commits category.

## Commit - object

Represents a Git commit.

**Implements:** GitObject, Node, Subscribable, UniformResourceLocatable

### Fields for `Commit`

* `abbreviatedOid` (String!): An abbreviated version of the Git object ID.
* `additions` (Int!): The number of additions in this commit.
* `associatedPullRequests` (PullRequestConnection): The merged Pull Request that introduced the commit to the repository. If the
commit is not present in the default branch, additionally returns open Pull
Requests associated with the commit.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (PullRequestOrder): Ordering options for pull requests.

* `author` (GitActor): Authorship details of the commit.
* `authoredByCommitter` (Boolean!): Check if the committer and the author match.
* `authoredDate` (DateTime!): The datetime when this commit was authored.
* `authors` (GitActorConnection!): The list of authors for this commit based on the git author and the Co-authored-by
message trailer. The git author will always be first. _(Pagination: `after`, `before`, `first`, `last`)_
* `blame` (Blame!): Fetches git blame information.
  * `path` (String!): The file whose Git blame information you want.

* `changedFiles` (Int!): We recommend using the changedFilesIfAvailable field instead of
changedFiles, as changedFiles will cause your request to return an error
if GitHub is unable to calculate the number of changed files. **Deprecated:** changedFiles will be removed. Use changedFilesIfAvailable instead. Removal on 2023-01-01 UTC.
* `changedFilesIfAvailable` (Int): The number of changed files in this commit. If GitHub is unable to calculate
the number of changed files (for example due to a timeout), this will return
null. We recommend using this field instead of changedFiles.
* `checkSuites` (CheckSuiteConnection): The check suites associated with a commit.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `filterBy` (CheckSuiteFilter): Filters the check suites by this type.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.

* `comments` (CommitCommentConnection!): Comments made on the commit. _(Pagination: `after`, `before`, `first`, `last`)_
* `commitResourcePath` (URI!): The HTTP path for this Git object.
* `commitUrl` (URI!): The HTTP URL for this Git object.
* `committedDate` (DateTime!): The datetime when this commit was committed.
* `committedViaWeb` (Boolean!): Check if committed via GitHub web UI.
* `committer` (GitActor): Committer details of the commit.
* `deletions` (Int!): The number of deletions in this commit.
* `deployments` (DeploymentConnection): The deployments associated with a commit.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `environments` ([String!]): Environments to list deployments for.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (DeploymentOrder): Ordering options for deployments returned from the connection.

* `file` (TreeEntry): The tree entry representing the file located at the given path.
  * `path` (String!): The path for the file.

* `history` (CommitHistoryConnection!): The linear commit history starting from (and including) this commit, in the same order as git log.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `author` (CommitAuthor): If non-null, filters history to only show commits with matching authorship.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `path` (String): If non-null, filters history to only show commits touching files under this path.
  * `since` (GitTimestamp): Allows specifying a beginning time or date for fetching commits. Unexpected
results may be returned for dates not between 1970-01-01 and 2099-12-13 (inclusive).
  * `until` (GitTimestamp): Allows specifying an ending time or date for fetching commits. Unexpected
results may be returned for dates not between 1970-01-01 and 2099-12-13 (inclusive).

* `id` (ID!): The Node ID of the Commit object.
* `message` (String!): The Git commit message.
* `messageBody` (String!): The Git commit message body.
* `messageBodyHTML` (HTML!): The commit message body rendered to HTML.
* `messageHeadline` (String!): The Git commit message headline.
* `messageHeadlineHTML` (HTML!): The commit message headline rendered to HTML.
* `oid` (GitObjectID!): The Git object ID.
* `onBehalfOf` (Organization): The organization this commit was made on behalf of.
* `parents` (CommitConnection!): The parents of a commit. _(Pagination: `after`, `before`, `first`, `last`)_
* `pushedDate` (DateTime): The datetime when this commit was pushed. **Deprecated:** pushedDate is no longer supported. Removal on 2023-07-01 UTC.
* `repository` (Repository!): The Repository this commit belongs to.
* `resourcePath` (URI!): The HTTP path for this commit.
* `signature` (GitSignature): Commit signing information, if present.
* `status` (Status): Status information for this commit.
* `statusCheckRollup` (StatusCheckRollup): Check and Status rollup information for this commit.
* `submodules` (SubmoduleConnection!): Returns a list of all submodules in this repository as of this Commit parsed from the .gitmodules file. _(Pagination: `after`, `before`, `first`, `last`)_
* `tarballUrl` (URI!): Returns a URL to download a tarball archive for a repository.
Note: For private repositories, these links are temporary and expire after five minutes.
* `tree` (Tree!): Commit's root Tree.
* `treeResourcePath` (URI!): The HTTP path for the tree of this commit.
* `treeUrl` (URI!): The HTTP URL for the tree of this commit.
* `url` (URI!): The HTTP URL for this commit.
* `viewerCanSubscribe` (Boolean!): Check if the viewer is able to change their subscription status for the repository.
* `viewerSubscription` (SubscriptionState): Identifies if the viewer is watching, not watching, or ignoring the subscribable entity.
* `zipballUrl` (URI!): Returns a URL to download a zipball archive for a repository.
Note: For private repositories, these links are temporary and expire after five minutes.

## CommitAuthor - input object

Specifies an author for filtering Git commits.

### Input fields for `CommitAuthor`

* `emails` ([String!]): Email addresses to filter by. Commits authored by any of the specified email addresses will be returned.
* `id` (ID): ID of a User to filter by. If non-null, only commits authored by this user
will be returned. This field takes precedence over emails.

## CommitAuthorEmailPatternParameters - object

Parameters to be used for the commit_author_email_pattern rule.

### Fields for `CommitAuthorEmailPatternParameters`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean!): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## CommitAuthorEmailPatternParametersInput - input object

Parameters to be used for the commit_author_email_pattern rule.

### Input fields for `CommitAuthorEmailPatternParametersInput`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## CommitComment - object

Represents a comment on a given Commit.

**Implements:** Comment, Deletable, Minimizable, Node, Reactable, RepositoryNode, Updatable, UpdatableComment

### Fields for `CommitComment`

* `author` (Actor): The actor who authored the comment.
* `authorAssociation` (CommentAuthorAssociation!): Author's association with the subject of the comment.
* `body` (String!): Identifies the comment body.
* `bodyHTML` (HTML!): The body rendered to HTML.
* `bodyText` (String!): The body rendered to text.
* `commit` (Commit): Identifies the commit associated with the comment, if the commit exists.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `createdViaEmail` (Boolean!): Check if this comment was created via an email reply.
* `databaseId` (Int): Identifies the primary key from the database.
* `editor` (Actor): The actor who edited the comment.
* `id` (ID!): The Node ID of the CommitComment object.
* `includesCreatedEdit` (Boolean!): Check if this comment was edited and includes an edit with the creation data.
* `isMinimized` (Boolean!): Returns whether or not a comment has been minimized.
* `lastEditedAt` (DateTime): The moment the editor made the last edit.
* `minimizedReason` (String): Returns why the comment was minimized. One of abuse, off-topic,
outdated, resolved, duplicate, spam, and low-quality. Note that the
case and formatting of these values differs from the inputs to the
MinimizeComment mutation.
* `path` (String): Identifies the file path associated with the comment.
* `position` (Int): Identifies the line position associated with the comment.
* `publishedAt` (DateTime): Identifies when the comment was published at.
* `reactionGroups` ([ReactionGroup!]): A list of reactions grouped by content left on the subject.
* `reactions` (ReactionConnection!): A list of Reactions left on the Issue.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `content` (ReactionContent): Allows filtering Reactions by emoji.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (ReactionOrder): Allows specifying the order in which reactions are returned.

* `repository` (Repository!): The repository associated with this node.
* `resourcePath` (URI!): The HTTP path permalink for this commit comment.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL permalink for this commit comment.
* `userContentEdits` (UserContentEditConnection): A list of edits to this content. _(Pagination: `after`, `before`, `first`, `last`)_
* `viewerCanDelete` (Boolean!): Check if the current viewer can delete this object.
* `viewerCanMinimize` (Boolean!): Check if the current viewer can minimize this object.
* `viewerCanReact` (Boolean!): Can user react to this subject.
* `viewerCanUnminimize` (Boolean!): Check if the current viewer can unminimize this object.
* `viewerCanUpdate` (Boolean!): Check if the current viewer can update this object.
* `viewerCannotUpdateReasons` ([CommentCannotUpdateReason!]!): Reasons why the current viewer can not update this comment.
* `viewerDidAuthor` (Boolean!): Did the viewer author this comment.

## CommitCommentConnection - object

The connection type for CommitComment.

### Fields for `CommitCommentConnection`

* `edges` ([CommitCommentEdge]): A list of edges.
* `nodes` ([CommitComment]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CommitCommentEdge - object

An edge in a connection.

### Fields for `CommitCommentEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CommitComment): The item at the end of the edge.

## CommitCommentThread - object

A thread of comments on a commit.

**Implements:** Node, RepositoryNode

### Fields for `CommitCommentThread`

* `comments` (CommitCommentConnection!): The comments that exist in this thread. _(Pagination: `after`, `before`, `first`, `last`)_
* `commit` (Commit): The commit the comments were made on.
* `id` (ID!): The Node ID of the CommitCommentThread object.
* `path` (String): The file the comments were made on.
* `position` (Int): The position in the diff for the commit that the comment was made on.
* `repository` (Repository!): The repository associated with this node.

## CommitConnection - object

The connection type for Commit.

### Fields for `CommitConnection`

* `edges` ([CommitEdge]): A list of edges.
* `nodes` ([Commit]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CommitContributionOrder - input object

Ordering options for commit contribution connections.

### Input fields for `CommitContributionOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (CommitContributionOrderField!): The field by which to order commit contributions.

## CommitContributionOrderField - enum

Properties by which commit contribution connections can be ordered.

### Values for `CommitContributionOrderField`

* `COMMIT_COUNT`: Order commit contributions by how many commits they represent.
* `OCCURRED_AT`: Order commit contributions by when they were made.

## CommitContributionsByRepository - object

This aggregates commits made by a user within one repository.

### Fields for `CommitContributionsByRepository`

* `contributions` (CreatedCommitContributionConnection!): The commit contributions, each representing a day.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (CommitContributionOrder): Ordering options for commit contributions returned from the connection.

* `repository` (Repository!): The repository in which the commits were made.
* `resourcePath` (URI!): The HTTP path for the user's commits to the repository in this time range.
* `url` (URI!): The HTTP URL for the user's commits to the repository in this time range.

## CommitEdge - object

An edge in a connection.

### Fields for `CommitEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (Commit): The item at the end of the edge.

## CommitHistoryConnection - object

The connection type for Commit.

### Fields for `CommitHistoryConnection`

* `edges` ([CommitEdge]): A list of edges.
* `nodes` ([Commit]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CommitMessage - input object

A message to include with a new commit.

### Input fields for `CommitMessage`

* `body` (String): The body of the message.
* `headline` (String!): The headline of the message.

## CommitMessagePatternParameters - object

Parameters to be used for the commit_message_pattern rule.

### Fields for `CommitMessagePatternParameters`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean!): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## CommitMessagePatternParametersInput - input object

Parameters to be used for the commit_message_pattern rule.

### Input fields for `CommitMessagePatternParametersInput`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## CommitterEmailPatternParameters - object

Parameters to be used for the committer_email_pattern rule.

### Fields for `CommitterEmailPatternParameters`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean!): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## CommitterEmailPatternParametersInput - input object

Parameters to be used for the committer_email_pattern rule.

### Input fields for `CommitterEmailPatternParametersInput`

* `name` (String): How this rule appears when configuring it.
* `negate` (Boolean): If true, the rule will fail if the pattern matches.
* `operator` (String!): The operator to use for matching.
* `pattern` (String!): The pattern to match with.

## Comparison - object

Represents a comparison between two commit revisions.

**Implements:** Node

### Fields for `Comparison`

* `aheadBy` (Int!): The number of commits ahead of the base branch.
* `baseTarget` (GitObject!): The base revision of this comparison.
* `behindBy` (Int!): The number of commits behind the base branch.
* `commits` (ComparisonCommitConnection!): The commits which compose this comparison. _(Pagination: `after`, `before`, `first`, `last`)_
* `headTarget` (GitObject!): The head revision of this comparison.
* `id` (ID!): The Node ID of the Comparison object.
* `status` (ComparisonStatus!): The status of this comparison.

## ComparisonCommitConnection - object

The connection type for Commit.

### Fields for `ComparisonCommitConnection`

* `authorCount` (Int!): The total count of authors and co-authors across all commits.
* `edges` ([CommitEdge]): A list of edges.
* `nodes` ([Commit]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## ComparisonStatus - enum

The status of a git comparison between two refs.

### Values for `ComparisonStatus`

* `AHEAD`: The head ref is ahead of the base ref.
* `BEHIND`: The head ref is behind the base ref.
* `DIVERGED`: The head ref is both ahead and behind of the base ref, indicating git history has diverged.
* `IDENTICAL`: The head ref and base ref are identical.

## createCommitOnBranch - mutation

Appends a commit to the given branch as the authenticated user.
This mutation creates a commit whose parent is the HEAD of the provided
branch and also updates that branch to point to the new commit.
It can be thought of as similar to git commit.
Locating a Branch
Commits are appended to a branch of type Ref.
This must refer to a git branch (i.e.  the fully qualified path must
begin with refs/heads/, although including this prefix is optional.
Callers may specify the branch to commit to either by its global node
ID or by passing both of repositoryNameWithOwner and refName.  For
more details see the documentation for CommittableBranch.
Describing Changes
fileChanges are specified as a FilesChanges object describing
FileAdditions and FileDeletions.
Please see the documentation for FileChanges for more information on
how to use this argument to describe any set of file changes.
Authorship
Similar to the web commit interface, this mutation does not support
specifying the author or committer of the commit and will not add
support for this in the future.
A commit created by a successful execution of this mutation will be
authored by the owner of the credential which authenticates the API
request.  The committer will be identical to that of commits authored
using the web interface.
If you need full control over author and committer information, please
use the Git Database REST API instead.
Commit Signing
Commits made using this mutation are automatically signed by GitHub if
supported and will be marked as verified in the user interface.

### Input fields for `createCommitOnBranch`

* `input` (CreateCommitOnBranchInput!): 

### Return fields for `createCommitOnBranch`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `commit` (Commit): The new commit.
* `ref` (Ref): The ref which has been updated to point to the new commit.

## CreateCommitOnBranchInput - input object

Autogenerated input type of CreateCommitOnBranch.

### Input fields for `CreateCommitOnBranchInput`

* `branch` (CommittableBranch!): The Ref to be updated.  Must be a branch.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `expectedHeadOid` (GitObjectID!): The git commit oid expected at the head of the branch prior to the commit.
* `fileChanges` (FileChanges): A description of changes to files in this commit.
* `message` (CommitMessage!): The commit message the be included with the commit.

## Status - object

Represents a commit status.

**Implements:** Node

### Fields for `Status`

* `combinedContexts` (StatusCheckRollupContextConnection!): A list of status contexts and check runs for this commit. _(Pagination: `after`, `before`, `first`, `last`)_
* `commit` (Commit): The commit this status is attached to.
* `context` (StatusContext): Looks up an individual status context by context name.
  * `name` (String!): The context name.

* `contexts` ([StatusContext!]!): The individual status contexts for this commit.
* `id` (ID!): The Node ID of the Status object.
* `state` (StatusState!): The combined commit status.

## StatusCheckConfiguration - object

Required status check.

### Fields for `StatusCheckConfiguration`

* `context` (String!): The status check context name that must be present on the commit.
* `integrationId` (Int): The optional integration ID that this status check must originate from.

## StatusCheckConfigurationInput - input object

Required status check.

### Input fields for `StatusCheckConfigurationInput`

* `context` (String!): The status check context name that must be present on the commit.
* `integrationId` (Int): The optional integration ID that this status check must originate from.

## StatusCheckRollup - object

Represents the rollup for both the check runs and status for a commit.

**Implements:** Node

### Fields for `StatusCheckRollup`

* `commit` (Commit): The commit the status and check runs are attached to.
* `contexts` (StatusCheckRollupContextConnection!): A list of status contexts and check runs for this commit. _(Pagination: `after`, `before`, `first`, `last`)_
* `id` (ID!): The Node ID of the StatusCheckRollup object.
* `state` (StatusState!): The combined status for the commit.

## StatusCheckRollupContext - union

Types that can be inside a StatusCheckRollup context.

### Possible types for `StatusCheckRollupContext`

* CheckRun
* StatusContext

## StatusCheckRollupContextConnection - object

The connection type for StatusCheckRollupContext.

### Fields for `StatusCheckRollupContextConnection`

* `checkRunCount` (Int!): The number of check runs in this rollup.
* `checkRunCountsByState` ([CheckRunStateCount!]): Counts of check runs by state.
* `edges` ([StatusCheckRollupContextEdge]): A list of edges.
* `nodes` ([StatusCheckRollupContext]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `statusContextCount` (Int!): The number of status contexts in this rollup.
* `statusContextCountsByState` ([StatusContextStateCount!]): Counts of status contexts by state.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## StatusCheckRollupContextEdge - object

An edge in a connection.

### Fields for `StatusCheckRollupContextEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (StatusCheckRollupContext): The item at the end of the edge.

## StatusContext - object

Represents an individual commit status context.

**Implements:** Node, RequirableByPullRequest

### Fields for `StatusContext`

* `avatarUrl` (URI): The avatar of the OAuth application or the user that created the status.
  * `size` (Int): The size of the resulting square image. Default: `40`.

* `commit` (Commit): This commit this status context is attached to.
* `context` (String!): The name of this status context.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `creator` (Actor): The actor who created this status context.
* `description` (String): The description for this status context.
* `id` (ID!): The Node ID of the StatusContext object.
* `isRequired` (Boolean!): Whether this is required to pass before merging for a specific pull request.
  * `pullRequestId` (ID): The id of the pull request this is required for.
  * `pullRequestNumber` (Int): The number of the pull request this is required for.

* `state` (StatusState!): The state of this status context.
* `targetUrl` (URI): The URL for this status context.

## StatusContextStateCount - object

Represents a count of the state of a status context.

### Fields for `StatusContextStateCount`

* `count` (Int!): The number of statuses with this state.
* `state` (StatusState!): The state of a status context.

## StatusState - enum

The possible commit status states.

### Values for `StatusState`

* `ERROR`: Status is errored.
* `EXPECTED`: Status is expected.
* `FAILURE`: Status is failing.
* `PENDING`: Status is pending.
* `SUCCESS`: Status is successful.