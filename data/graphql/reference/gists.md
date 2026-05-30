# Gists

Reference documentation for GraphQL schema types in the Gists category.

## Gist - object

A Gist.

**Implements:** Node, Starrable, UniformResourceLocatable

### Fields for `Gist`

* `comments` (GistCommentConnection!): A list of comments associated with the gist. _(Pagination: `after`, `before`, `first`, `last`)_
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `description` (String): The gist description.
* `files` ([GistFile]): The files in this gist.
  * `limit` (Int): The maximum number of files to return. Default: `10`.
  * `oid` (GitObjectID): The oid of the files to return.

* `forks` (GistConnection!): A list of forks associated with the gist.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (GistOrder): Ordering options for gists returned from the connection.

* `id` (ID!): The Node ID of the Gist object.
* `isFork` (Boolean!): Identifies if the gist is a fork.
* `isPublic` (Boolean!): Whether the gist is public or not.
* `name` (String!): The gist name.
* `owner` (RepositoryOwner): The gist owner.
* `pushedAt` (DateTime): Identifies when the gist was last pushed to.
* `resourcePath` (URI!): The HTML path to this resource.
* `stargazerCount` (Int!): Returns a count of how many stargazers there are on this object.
* `stargazers` (StargazerConnection!): A list of users who have starred this starrable.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (StarOrder): Order for connection.

* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this Gist.
* `viewerHasStarred` (Boolean!): Returns a boolean indicating whether the viewing user has starred this starrable.

## GistComment - object

Represents a comment on an Gist.

**Implements:** Comment, Deletable, Minimizable, Node, Updatable, UpdatableComment

### Fields for `GistComment`

* `author` (Actor): The actor who authored the comment.
* `authorAssociation` (CommentAuthorAssociation!): Author's association with the gist.
* `body` (String!): Identifies the comment body.
* `bodyHTML` (HTML!): The body rendered to HTML.
* `bodyText` (String!): The body rendered to text.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `createdViaEmail` (Boolean!): Check if this comment was created via an email reply.
* `databaseId` (Int): Identifies the primary key from the database.
* `editor` (Actor): The actor who edited the comment.
* `gist` (Gist!): The associated gist.
* `id` (ID!): The Node ID of the GistComment object.
* `includesCreatedEdit` (Boolean!): Check if this comment was edited and includes an edit with the creation data.
* `isMinimized` (Boolean!): Returns whether or not a comment has been minimized.
* `lastEditedAt` (DateTime): The moment the editor made the last edit.
* `minimizedReason` (String): Returns why the comment was minimized. One of abuse, off-topic,
outdated, resolved, duplicate, spam, and low-quality. Note that the
case and formatting of these values differs from the inputs to the
MinimizeComment mutation.
* `publishedAt` (DateTime): Identifies when the comment was published at.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `userContentEdits` (UserContentEditConnection): A list of edits to this content. _(Pagination: `after`, `before`, `first`, `last`)_
* `viewerCanDelete` (Boolean!): Check if the current viewer can delete this object.
* `viewerCanMinimize` (Boolean!): Check if the current viewer can minimize this object.
* `viewerCanUnminimize` (Boolean!): Check if the current viewer can unminimize this object.
* `viewerCanUpdate` (Boolean!): Check if the current viewer can update this object.
* `viewerCannotUpdateReasons` ([CommentCannotUpdateReason!]!): Reasons why the current viewer can not update this comment.
* `viewerDidAuthor` (Boolean!): Did the viewer author this comment.

## GistCommentConnection - object

The connection type for GistComment.

### Fields for `GistCommentConnection`

* `edges` ([GistCommentEdge]): A list of edges.
* `nodes` ([GistComment]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## GistCommentEdge - object

An edge in a connection.

### Fields for `GistCommentEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (GistComment): The item at the end of the edge.

## GistConnection - object

The connection type for Gist.

### Fields for `GistConnection`

* `edges` ([GistEdge]): A list of edges.
* `nodes` ([Gist]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## GistEdge - object

An edge in a connection.

### Fields for `GistEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (Gist): The item at the end of the edge.

## GistFile - object

A file in a gist.

### Fields for `GistFile`

* `encodedName` (String): The file name encoded to remove characters that are invalid in URL paths.
* `encoding` (String): The gist file encoding.
* `extension` (String): The file extension from the file name.
* `isImage` (Boolean!): Indicates if this file is an image.
* `isTruncated` (Boolean!): Whether the file's contents were truncated.
* `language` (Language): The programming language this file is written in.
* `name` (String): The gist file name.
* `size` (Int): The gist file size in bytes.
* `text` (String): UTF8 text data or null if the file is binary.
  * `truncate` (Int): Optionally truncate the returned file to this length.

## GistOrder - input object

Ordering options for gist connections.

### Input fields for `GistOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (GistOrderField!): The field to order repositories by.

## GistOrderField - enum

Properties by which gist connections can be ordered.

### Values for `GistOrderField`

* `CREATED_AT`: Order gists by creation time.
* `PUSHED_AT`: Order gists by push time.
* `UPDATED_AT`: Order gists by update time.

## GistPrivacy - enum

The privacy of a Gist.

### Values for `GistPrivacy`

* `ALL`: Gists that are public and secret.
* `PUBLIC`: Public.
* `SECRET`: Secret.