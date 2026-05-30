# Releases

Reference documentation for GraphQL schema types in the Releases category.

## Release - object

A release contains the content for a release.

**Implements:** Node, Reactable, UniformResourceLocatable

### Fields for `Release`

* `author` (User): The author of the release.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `description` (String): The description of the release.
* `descriptionHTML` (HTML): The description of this release rendered to HTML.
* `id` (ID!): The Node ID of the Release object.
* `immutable` (Boolean!): Whether or not the release is immutable.
* `isDraft` (Boolean!): Whether or not the release is a draft.
* `isLatest` (Boolean!): Whether or not the release is the latest releast.
* `isPrerelease` (Boolean!): Whether or not the release is a prerelease.
* `mentions` (UserConnection): A list of users mentioned in the release description. _(Pagination: `after`, `before`, `first`, `last`)_
* `name` (String): The title of the release.
* `publishedAt` (DateTime): Identifies the date and time when the release was created.
* `reactionGroups` ([ReactionGroup!]): A list of reactions grouped by content left on the subject.
* `reactions` (ReactionConnection!): A list of Reactions left on the Issue.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `content` (ReactionContent): Allows filtering Reactions by emoji.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (ReactionOrder): Allows specifying the order in which reactions are returned.

* `releaseAssets` (ReleaseAssetConnection!): List of releases assets which are dependent on this release.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `name` (String): A name to filter the assets by.

* `repository` (Repository!): The repository that the release belongs to.
* `resourcePath` (URI!): The HTTP path for this issue.
* `shortDescriptionHTML` (HTML): A description of the release, rendered to HTML without any links in it.
  * `limit` (Int): How many characters to return. Default: `200`.

* `tag` (Ref): The Git tag the release points to.
* `tagCommit` (Commit): The tag commit for this release.
* `tagName` (String!): The name of the release's Git tag.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this issue.
* `viewerCanReact` (Boolean!): Can user react to this subject.

## ReleaseAsset - object

A release asset contains the content for a release asset.

**Implements:** Node

### Fields for `ReleaseAsset`

* `contentType` (String!): The asset's content-type.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `digest` (String): The SHA256 digest of the asset.
* `downloadCount` (Int!): The number of times this asset was downloaded.
* `downloadUrl` (URI!): Identifies the URL where you can download the release asset via the browser.
* `id` (ID!): The Node ID of the ReleaseAsset object.
* `name` (String!): Identifies the title of the release asset.
* `release` (Release): Release that the asset is associated with.
* `size` (Int!): The size (in bytes) of the asset.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `uploadedBy` (User!): The user that performed the upload.
* `url` (URI!): Identifies the URL of the release asset.

## ReleaseAssetConnection - object

The connection type for ReleaseAsset.

### Fields for `ReleaseAssetConnection`

* `edges` ([ReleaseAssetEdge]): A list of edges.
* `nodes` ([ReleaseAsset]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## ReleaseAssetEdge - object

An edge in a connection.

### Fields for `ReleaseAssetEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (ReleaseAsset): The item at the end of the edge.

## ReleaseConnection - object

The connection type for Release.

### Fields for `ReleaseConnection`

* `edges` ([ReleaseEdge]): A list of edges.
* `nodes` ([Release]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## ReleaseEdge - object

An edge in a connection.

### Fields for `ReleaseEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (Release): The item at the end of the edge.

## ReleaseOrder - input object

Ways in which lists of releases can be ordered upon return.

### Input fields for `ReleaseOrder`

* `direction` (OrderDirection!): The direction in which to order releases by the specified field.
* `field` (ReleaseOrderField!): The field in which to order releases by.

## ReleaseOrderField - enum

Properties by which release connections can be ordered.

### Values for `ReleaseOrderField`

* `CREATED_AT`: Order releases by creation time.
* `NAME`: Order releases alphabetically by name.