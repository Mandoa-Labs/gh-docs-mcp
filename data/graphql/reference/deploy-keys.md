# Deploy keys

Reference documentation for GraphQL schema types in the Deploy keys category.

## DeployKey - object

A repository deploy key.

**Implements:** Node

### Fields for `DeployKey`

* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `enabled` (Boolean!): Whether or not the deploy key is enabled by policy at the Enterprise or Organization level.
* `id` (ID!): The Node ID of the DeployKey object.
* `key` (String!): The deploy key.
* `readOnly` (Boolean!): Whether or not the deploy key is read only.
* `title` (String!): The deploy key title.
* `verified` (Boolean!): Whether or not the deploy key has been verified.

## DeployKeyConnection - object

The connection type for DeployKey.

### Fields for `DeployKeyConnection`

* `edges` ([DeployKeyEdge]): A list of edges.
* `nodes` ([DeployKey]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## DeployKeyEdge - object

An edge in a connection.

### Fields for `DeployKeyEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (DeployKey): The item at the end of the edge.