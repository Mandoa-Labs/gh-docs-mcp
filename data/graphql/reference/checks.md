# Checks

Reference documentation for GraphQL schema types in the Checks category.

## CheckAnnotation - object

A single check annotation.

### Fields for `CheckAnnotation`

* `annotationLevel` (CheckAnnotationLevel): The annotation's severity level.
* `blobUrl` (URI!): The path to the file that this annotation was made on.
* `databaseId` (Int): Identifies the primary key from the database. **Deprecated:** databaseId will be removed because it does not support 64-bit signed integer identifiers. Use fullDatabaseId instead. Removal on 2027-01-01 UTC.
* `fullDatabaseId` (BigInt): Identifies the primary key from the database as a BigInt.
* `location` (CheckAnnotationSpan!): The position of this annotation.
* `message` (String!): The annotation's message.
* `path` (String!): The path that this annotation was made on.
* `rawDetails` (String): Additional information about the annotation.
* `title` (String): The annotation's title.

## CheckAnnotationConnection - object

The connection type for CheckAnnotation.

### Fields for `CheckAnnotationConnection`

* `edges` ([CheckAnnotationEdge]): A list of edges.
* `nodes` ([CheckAnnotation]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CheckAnnotationData - input object

Information from a check run analysis to specific lines of code.

### Input fields for `CheckAnnotationData`

* `annotationLevel` (CheckAnnotationLevel!): Represents an annotation's information level.
* `location` (CheckAnnotationRange!): The location of the annotation.
* `message` (String!): A short description of the feedback for these lines of code.
* `path` (String!): The path of the file to add an annotation to.
* `rawDetails` (String): Details about this annotation.
* `title` (String): The title that represents the annotation.

## CheckAnnotationEdge - object

An edge in a connection.

### Fields for `CheckAnnotationEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CheckAnnotation): The item at the end of the edge.

## CheckAnnotationLevel - enum

Represents an annotation's information level.

### Values for `CheckAnnotationLevel`

* `FAILURE`: An annotation indicating an inescapable error.
* `NOTICE`: An annotation indicating some information.
* `WARNING`: An annotation indicating an ignorable error.

## CheckAnnotationPosition - object

A character position in a check annotation.

### Fields for `CheckAnnotationPosition`

* `column` (Int): Column number (1 indexed).
* `line` (Int!): Line number (1 indexed).

## CheckAnnotationRange - input object

Information from a check run analysis to specific lines of code.

### Input fields for `CheckAnnotationRange`

* `endColumn` (Int): The ending column of the range.
* `endLine` (Int!): The ending line of the range.
* `startColumn` (Int): The starting column of the range.
* `startLine` (Int!): The starting line of the range.

## CheckAnnotationSpan - object

An inclusive pair of positions for a check annotation.

### Fields for `CheckAnnotationSpan`

* `end` (CheckAnnotationPosition!): End position (inclusive).
* `start` (CheckAnnotationPosition!): Start position (inclusive).

## CheckConclusionState - enum

The possible states for a check suite or run conclusion.

### Values for `CheckConclusionState`

* `ACTION_REQUIRED`: The check suite or run requires action.
* `CANCELLED`: The check suite or run has been cancelled.
* `FAILURE`: The check suite or run has failed.
* `NEUTRAL`: The check suite or run was neutral.
* `SKIPPED`: The check suite or run was skipped.
* `STALE`: The check suite or run was marked stale by GitHub. Only GitHub can use this conclusion.
* `STARTUP_FAILURE`: The check suite or run has failed at startup.
* `SUCCESS`: The check suite or run has succeeded.
* `TIMED_OUT`: The check suite or run has timed out.

## CheckRun - object

A check run.

**Implements:** Node, RequirableByPullRequest, UniformResourceLocatable

### Fields for `CheckRun`

* `annotations` (CheckAnnotationConnection): The check run's annotations. _(Pagination: `after`, `before`, `first`, `last`)_
* `checkSuite` (CheckSuite!): The check suite that this run is a part of.
* `completedAt` (DateTime): Identifies the date and time when the check run was completed.
* `conclusion` (CheckConclusionState): The conclusion of the check run.
* `databaseId` (Int): Identifies the primary key from the database.
* `deployment` (Deployment): The corresponding deployment for this job, if any.
* `detailsUrl` (URI): The URL from which to find full details of the check run on the integrator's site.
* `externalId` (String): A reference for the check run on the integrator's system.
* `id` (ID!): The Node ID of the CheckRun object.
* `isRequired` (Boolean!): Whether this is required to pass before merging for a specific pull request.
  * `pullRequestId` (ID): The id of the pull request this is required for.
  * `pullRequestNumber` (Int): The number of the pull request this is required for.

* `name` (String!): The name of the check for this check run.
* `pendingDeploymentRequest` (DeploymentRequest): Information about a pending deployment, if any, in this check run.
* `permalink` (URI!): The permalink to the check run summary.
* `repository` (Repository!): The repository associated with this check run.
* `resourcePath` (URI!): The HTTP path for this check run.
* `startedAt` (DateTime): Identifies the date and time when the check run was started.
* `status` (CheckStatusState!): The current status of the check run.
* `steps` (CheckStepConnection): The check run's steps.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `number` (Int): Step number.

* `summary` (String): A string representing the check run's summary.
* `text` (String): A string representing the check run's text.
* `title` (String): A string representing the check run.
* `url` (URI!): The HTTP URL for this check run.

## CheckRunAction - input object

Possible further actions the integrator can perform.

### Input fields for `CheckRunAction`

* `description` (String!): A short explanation of what this action would do.
* `identifier` (String!): A reference for the action on the integrator's system.
* `label` (String!): The text to be displayed on a button in the web UI.

## CheckRunConnection - object

The connection type for CheckRun.

### Fields for `CheckRunConnection`

* `edges` ([CheckRunEdge]): A list of edges.
* `nodes` ([CheckRun]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CheckRunEdge - object

An edge in a connection.

### Fields for `CheckRunEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CheckRun): The item at the end of the edge.

## CheckRunFilter - input object

The filters that are available when fetching check runs.

### Input fields for `CheckRunFilter`

* `appId` (Int): Filters the check runs created by this application ID.
* `checkName` (String): Filters the check runs by this name.
* `checkType` (CheckRunType): Filters the check runs by this type.
* `conclusions` ([CheckConclusionState!]): Filters the check runs by these conclusions.
* `status` (CheckStatusState): Filters the check runs by this status. Superceded by statuses.
* `statuses` ([CheckStatusState!]): Filters the check runs by this status. Overrides status.

## CheckRunOutput - input object

Descriptive details about the check run.

### Input fields for `CheckRunOutput`

* `annotations` ([CheckAnnotationData!]): The annotations that are made as part of the check run.
* `images` ([CheckRunOutputImage!]): Images attached to the check run output displayed in the GitHub pull request UI.
* `summary` (String!): The summary of the check run (supports Commonmark).
* `text` (String): The details of the check run (supports Commonmark).
* `title` (String!): A title to provide for this check run.

## CheckRunOutputImage - input object

Images attached to the check run output displayed in the GitHub pull request UI.

### Input fields for `CheckRunOutputImage`

* `alt` (String!): The alternative text for the image.
* `caption` (String): A short image description.
* `imageUrl` (URI!): The full URL of the image.

## CheckRunState - enum

The possible states of a check run in a status rollup.

### Values for `CheckRunState`

* `ACTION_REQUIRED`: The check run requires action.
* `CANCELLED`: The check run has been cancelled.
* `COMPLETED`: The check run has been completed.
* `FAILURE`: The check run has failed.
* `IN_PROGRESS`: The check run is in progress.
* `NEUTRAL`: The check run was neutral.
* `PENDING`: The check run is in pending state.
* `QUEUED`: The check run has been queued.
* `SKIPPED`: The check run was skipped.
* `STALE`: The check run was marked stale by GitHub. Only GitHub can use this conclusion.
* `STARTUP_FAILURE`: The check run has failed at startup.
* `SUCCESS`: The check run has succeeded.
* `TIMED_OUT`: The check run has timed out.
* `WAITING`: The check run is in waiting state.

## CheckRunStateCount - object

Represents a count of the state of a check run.

### Fields for `CheckRunStateCount`

* `count` (Int!): The number of check runs with this state.
* `state` (CheckRunState!): The state of a check run.

## CheckRunType - enum

The possible types of check runs.

### Values for `CheckRunType`

* `ALL`: Every check run available.
* `LATEST`: The latest check run.

## CheckStatusState - enum

The possible states for a check suite or run status.

### Values for `CheckStatusState`

* `COMPLETED`: The check suite or run has been completed.
* `IN_PROGRESS`: The check suite or run is in progress.
* `PENDING`: The check suite or run is in pending state.
* `QUEUED`: The check suite or run has been queued.
* `REQUESTED`: The check suite or run has been requested.
* `WAITING`: The check suite or run is in waiting state.

## CheckStep - object

A single check step.

### Fields for `CheckStep`

* `completedAt` (DateTime): Identifies the date and time when the check step was completed.
* `conclusion` (CheckConclusionState): The conclusion of the check step.
* `externalId` (String): A reference for the check step on the integrator's system.
* `name` (String!): The step's name.
* `number` (Int!): The index of the step in the list of steps of the parent check run.
* `secondsToCompletion` (Int): Number of seconds to completion.
* `startedAt` (DateTime): Identifies the date and time when the check step was started.
* `status` (CheckStatusState!): The current status of the check step.

## CheckStepConnection - object

The connection type for CheckStep.

### Fields for `CheckStepConnection`

* `edges` ([CheckStepEdge]): A list of edges.
* `nodes` ([CheckStep]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CheckStepEdge - object

An edge in a connection.

### Fields for `CheckStepEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CheckStep): The item at the end of the edge.

## CheckSuite - object

A check suite.

**Implements:** Node

### Fields for `CheckSuite`

* `app` (App): The GitHub App which created this check suite.
* `branch` (Ref): The name of the branch for this check suite.
* `checkRuns` (CheckRunConnection): The check runs associated with a check suite.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `filterBy` (CheckRunFilter): Filters the check runs by this type.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.

* `commit` (Commit!): The commit for this check suite.
* `conclusion` (CheckConclusionState): The conclusion of this check suite.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `creator` (User): The user who triggered the check suite.
* `databaseId` (Int): Identifies the primary key from the database.
* `id` (ID!): The Node ID of the CheckSuite object.
* `matchingPullRequests` (PullRequestConnection): A list of open pull requests matching the check suite.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `baseRefName` (String): The base ref name to filter the pull requests by.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `headRefName` (String): The head ref name to filter the pull requests by.
  * `labels` ([String!]): A list of label names to filter the pull requests by.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (IssueOrder): Ordering options for pull requests returned from the connection.
  * `states` ([PullRequestState!]): A list of states to filter the pull requests by.

* `push` (Push): The push that triggered this check suite.
* `repository` (Repository!): The repository associated with this check suite.
* `resourcePath` (URI!): The HTTP path for this check suite.
* `status` (CheckStatusState!): The status of this check suite.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this check suite.
* `workflowRun` (WorkflowRun): The workflow run associated with this check suite.

## CheckSuiteAutoTriggerPreference - input object

The auto-trigger preferences that are available for check suites.

### Input fields for `CheckSuiteAutoTriggerPreference`

* `appId` (ID!): The node ID of the application that owns the check suite.
* `setting` (Boolean!): Set to true to enable automatic creation of CheckSuite events upon pushes to the repository.

## CheckSuiteConnection - object

The connection type for CheckSuite.

### Fields for `CheckSuiteConnection`

* `edges` ([CheckSuiteEdge]): A list of edges.
* `nodes` ([CheckSuite]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CheckSuiteEdge - object

An edge in a connection.

### Fields for `CheckSuiteEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CheckSuite): The item at the end of the edge.

## CheckSuiteFilter - input object

The filters that are available when fetching check suites.

### Input fields for `CheckSuiteFilter`

* `appId` (Int): Filters the check suites created by this application ID.
* `checkName` (String): Filters the check suites by this name.

## createCheckRun - mutation

Create a check run.

### Input fields for `createCheckRun`

* `input` (CreateCheckRunInput!): 

### Return fields for `createCheckRun`

* `checkRun` (CheckRun): The newly created check run.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## CreateCheckRunInput - input object

Autogenerated input type of CreateCheckRun.

### Input fields for `CreateCheckRunInput`

* `actions` ([CheckRunAction!]): Possible further actions the integrator can perform, which a user may trigger.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `completedAt` (DateTime): The time that the check run finished.
* `conclusion` (CheckConclusionState): The final conclusion of the check.
* `detailsUrl` (URI): The URL of the integrator's site that has the full details of the check.
* `externalId` (String): A reference for the run on the integrator's system.
* `headSha` (GitObjectID!): The SHA of the head commit.
* `name` (String!): The name of the check.
* `output` (CheckRunOutput): Descriptive details about the run.
* `repositoryId` (ID!): The node ID of the repository.
* `startedAt` (DateTime): The time that the check run began.
* `status` (RequestableCheckStatusState): The current status.

## createCheckSuite - mutation

Create a check suite.

### Input fields for `createCheckSuite`

* `input` (CreateCheckSuiteInput!): 

### Return fields for `createCheckSuite`

* `checkSuite` (CheckSuite): The newly created check suite.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## CreateCheckSuiteInput - input object

Autogenerated input type of CreateCheckSuite.

### Input fields for `CreateCheckSuiteInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `headSha` (GitObjectID!): The SHA of the head commit.
* `repositoryId` (ID!): The Node ID of the repository.

## RequestableCheckStatusState - enum

The possible states that can be requested when creating a check run.

### Values for `RequestableCheckStatusState`

* `COMPLETED`: The check suite or run has been completed.
* `IN_PROGRESS`: The check suite or run is in progress.
* `PENDING`: The check suite or run is in pending state.
* `QUEUED`: The check suite or run has been queued.
* `WAITING`: The check suite or run is in waiting state.

## rerequestCheckSuite - mutation

Rerequests an existing check suite.

### Input fields for `rerequestCheckSuite`

* `input` (RerequestCheckSuiteInput!): 

### Return fields for `rerequestCheckSuite`

* `checkSuite` (CheckSuite): The requested check suite.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## RerequestCheckSuiteInput - input object

Autogenerated input type of RerequestCheckSuite.

### Input fields for `RerequestCheckSuiteInput`

* `checkSuiteId` (ID!): The Node ID of the check suite.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `repositoryId` (ID!): The Node ID of the repository.

## updateCheckRun - mutation

Update a check run.

### Input fields for `updateCheckRun`

* `input` (UpdateCheckRunInput!): 

### Return fields for `updateCheckRun`

* `checkRun` (CheckRun): The updated check run.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.

## UpdateCheckRunInput - input object

Autogenerated input type of UpdateCheckRun.

### Input fields for `UpdateCheckRunInput`

* `actions` ([CheckRunAction!]): Possible further actions the integrator can perform, which a user may trigger.
* `checkRunId` (ID!): The node of the check.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `completedAt` (DateTime): The time that the check run finished.
* `conclusion` (CheckConclusionState): The final conclusion of the check.
* `detailsUrl` (URI): The URL of the integrator's site that has the full details of the check.
* `externalId` (String): A reference for the run on the integrator's system.
* `name` (String): The name of the check.
* `output` (CheckRunOutput): Descriptive details about the run.
* `repositoryId` (ID!): The node ID of the repository.
* `startedAt` (DateTime): The time that the check run began.
* `status` (RequestableCheckStatusState): The current status.

## updateCheckSuitePreferences - mutation

Modifies the settings of an existing check suite.

### Input fields for `updateCheckSuitePreferences`

* `input` (UpdateCheckSuitePreferencesInput!): 

### Return fields for `updateCheckSuitePreferences`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `repository` (Repository): The updated repository.

## UpdateCheckSuitePreferencesInput - input object

Autogenerated input type of UpdateCheckSuitePreferences.

### Input fields for `UpdateCheckSuitePreferencesInput`

* `autoTriggerPreferences` ([CheckSuiteAutoTriggerPreference!]!): The check suite preferences to modify.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `repositoryId` (ID!): The Node ID of the repository.