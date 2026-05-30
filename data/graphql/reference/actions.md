# Actions

Reference documentation for GraphQL schema types in the Actions category.

## Workflow - object

A workflow contains meta information about an Actions workflow file.

**Implements:** Node, UniformResourceLocatable

### Fields for `Workflow`

* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `id` (ID!): The Node ID of the Workflow object.
* `name` (String!): The name of the workflow.
* `resourcePath` (URI!): The HTTP path for this workflow.
* `runs` (WorkflowRunConnection!): The runs of the workflow.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (WorkflowRunOrder): Ordering options for the connection.

* `state` (WorkflowState!): The state of the workflow.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this workflow.

## WorkflowFileReference - object

A workflow that must run for this rule to pass.

### Fields for `WorkflowFileReference`

* `path` (String!): The path to the workflow file.
* `ref` (String): The ref (branch or tag) of the workflow file to use.
* `repositoryId` (Int!): The ID of the repository where the workflow is defined.
* `sha` (String): The commit SHA of the workflow file to use.

## WorkflowFileReferenceInput - input object

A workflow that must run for this rule to pass.

### Input fields for `WorkflowFileReferenceInput`

* `path` (String!): The path to the workflow file.
* `ref` (String): The ref (branch or tag) of the workflow file to use.
* `repositoryId` (Int!): The ID of the repository where the workflow is defined.
* `sha` (String): The commit SHA of the workflow file to use.

## WorkflowRun - object

A workflow run.

**Implements:** Node, UniformResourceLocatable

### Fields for `WorkflowRun`

* `checkSuite` (CheckSuite!): The check suite this workflow run belongs to.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `deploymentReviews` (DeploymentReviewConnection!): The log of deployment reviews. _(Pagination: `after`, `before`, `first`, `last`)_
* `event` (String!): The event that triggered the workflow run.
* `file` (WorkflowRunFile): The workflow file.
* `id` (ID!): The Node ID of the WorkflowRun object.
* `pendingDeploymentRequests` (DeploymentRequestConnection!): The pending deployment requests of all check runs in this workflow run. _(Pagination: `after`, `before`, `first`, `last`)_
* `resourcePath` (URI!): The HTTP path for this workflow run.
* `runNumber` (Int!): A number that uniquely identifies this workflow run in its parent workflow.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this workflow run.
* `workflow` (Workflow!): The workflow executed in this workflow run.

## WorkflowRunConnection - object

The connection type for WorkflowRun.

### Fields for `WorkflowRunConnection`

* `edges` ([WorkflowRunEdge]): A list of edges.
* `nodes` ([WorkflowRun]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## WorkflowRunEdge - object

An edge in a connection.

### Fields for `WorkflowRunEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (WorkflowRun): The item at the end of the edge.

## WorkflowRunFile - object

An executed workflow file for a workflow run.

**Implements:** Node, UniformResourceLocatable

### Fields for `WorkflowRunFile`

* `id` (ID!): The Node ID of the WorkflowRunFile object.
* `path` (String!): The path of the workflow file relative to its repository.
* `repositoryFileUrl` (URI!): The direct link to the file in the repository which stores the workflow file.
* `repositoryName` (URI!): The repository name and owner which stores the workflow file.
* `resourcePath` (URI!): The HTTP path for this workflow run file.
* `run` (WorkflowRun!): The parent workflow run execution for this file.
* `url` (URI!): The HTTP URL for this workflow run file.
* `viewerCanPushRepository` (Boolean!): If the viewer has permissions to push to the repository which stores the workflow.
* `viewerCanReadRepository` (Boolean!): If the viewer has permissions to read the repository which stores the workflow.

## WorkflowRunOrder - input object

Ways in which lists of workflow runs can be ordered upon return.

### Input fields for `WorkflowRunOrder`

* `direction` (OrderDirection!): The direction in which to order workflow runs by the specified field.
* `field` (WorkflowRunOrderField!): The field by which to order workflows.

## WorkflowRunOrderField - enum

Properties by which workflow run connections can be ordered.

### Values for `WorkflowRunOrderField`

* `CREATED_AT`: Order workflow runs by most recently created.

## WorkflowsParameters - object

Require all changes made to a targeted branch to pass the specified workflows before they can be merged.

### Fields for `WorkflowsParameters`

* `doNotEnforceOnCreate` (Boolean!): Allow repositories and branches to be created if a check would otherwise prohibit it.
* `workflows` ([WorkflowFileReference!]!): Workflows that must pass for this rule to pass.

## WorkflowsParametersInput - input object

Require all changes made to a targeted branch to pass the specified workflows before they can be merged.

### Input fields for `WorkflowsParametersInput`

* `doNotEnforceOnCreate` (Boolean): Allow repositories and branches to be created if a check would otherwise prohibit it.
* `workflows` ([WorkflowFileReferenceInput!]!): Workflows that must pass for this rule to pass.

## WorkflowState - enum

The possible states for a workflow.

### Values for `WorkflowState`

* `ACTIVE`: The workflow is active.
* `DELETED`: The workflow was deleted from the git repository.
* `DISABLED_FORK`: The workflow was disabled by default on a fork.
* `DISABLED_INACTIVITY`: The workflow was disabled for inactivity in the repository.
* `DISABLED_MANUALLY`: The workflow was disabled manually.