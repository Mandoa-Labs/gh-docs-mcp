# Search

Reference documentation for GraphQL schema types in the Search category.

## LexicalFallbackReason - enum

Reason why a semantic or hybrid issue search fell back to lexical search.

### Values for `LexicalFallbackReason`

* `NON_ISSUE_TARGET`: Query targets non-issue types (e.g., pull requests).
* `NO_ACCESSIBLE_REPOS`: Scoped query resolved to zero accessible repositories.
* `NO_TEXT_TERMS`: Query has only qualifiers and no free text terms.
* `ONLY_NON_SEMANTIC_FIELDS_REQUESTED`: Query uses an in: qualifier targeting non-semantic fields.
* `OR_BOOLEAN_NOT_SUPPORTED`: Query contains OR operators (nested boolean qualifiers).
* `QUOTED_TEXT`: Query contains quoted text requiring exact matches.
* `SERVER_ERROR`: Embedding generation failed or timed out.

## search - query

Perform a search across resources, returning a maximum of 1,000 results.

**Type:** SearchResultItemConnection!

### Arguments for `search`

* `after` (String): Returns the elements in the list that come after the specified cursor.
* `before` (String): Returns the elements in the list that come before the specified cursor.
* `first` (Int): Returns the first n elements from the list.
* `last` (Int): Returns the last n elements from the list.
* `query` (String!): The search string to look for. GitHub search syntax is supported. For more
information, see "Searching on
GitHub,"
"Understanding the search syntax,"
and "Sorting search results.".
* `type` (SearchType!): The types of search items to search within.

## SearchResultItem - union

The results of a search.

### Possible types for `SearchResultItem`

* App
* Discussion
* Issue
* MarketplaceListing
* Organization
* PullRequest
* Repository
* User

## SearchResultItemConnection - object

A list of results that matched against a search query. Regardless of the number
of matches, a maximum of 1,000 results will be available across all types,
potentially split across many pages.

### Fields for `SearchResultItemConnection`

* `codeCount` (Int!): The total number of pieces of code that matched the search query. Regardless
of the total number of matches, a maximum of 1,000 results will be available
across all types.
* `discussionCount` (Int!): The total number of discussions that matched the search query. Regardless of
the total number of matches, a maximum of 1,000 results will be available
across all types.
* `edges` ([SearchResultItemEdge]): A list of edges.
* `issueCount` (Int!): The total number of issues that matched the search query. Regardless of the
total number of matches, a maximum of 1,000 results will be available across all types.
* `issueSearchType` (IssueSearchType): The type of search that was performed for issues (lexical, semantic, or hybrid).
* `lexicalFallbackReason` ([LexicalFallbackReason!]): When a semantic or hybrid search falls back to lexical, the reasons why the fallback occurred.
* `nodes` ([SearchResultItem]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `repositoryCount` (Int!): The total number of repositories that matched the search query. Regardless of
the total number of matches, a maximum of 1,000 results will be available
across all types.
* `userCount` (Int!): The total number of users that matched the search query. Regardless of the
total number of matches, a maximum of 1,000 results will be available across all types.
* `wikiCount` (Int!): The total number of wiki pages that matched the search query. Regardless of
the total number of matches, a maximum of 1,000 results will be available
across all types.

## SearchResultItemEdge - object

An edge in a connection.

### Fields for `SearchResultItemEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (SearchResultItem): The item at the end of the edge.
* `textMatches` ([TextMatch]): Text matches on the result found.

## SearchType - enum

Represents the individual results of a search.

### Values for `SearchType`

* `DISCUSSION`: Returns matching discussions in repositories.
* `ISSUE`: Returns results matching issues in repositories.
* `ISSUE_ADVANCED`: Returns results matching issues in repositories.
* `ISSUE_HYBRID`: Returns results matching issues using hybrid (lexical + semantic) search.
* `ISSUE_SEMANTIC`: Returns results matching issues using semantic search.
* `REPOSITORY`: Returns results matching repositories.
* `USER`: Returns results matching users and organizations on GitHub.

## TextMatch - object

A text match within a search result.

### Fields for `TextMatch`

* `fragment` (String!): The specific text fragment within the property matched on.
* `highlights` ([TextMatchHighlight!]!): Highlights within the matched fragment.
* `property` (String!): The property matched on.

## TextMatchHighlight - object

Represents a single highlight in a search result match.

### Fields for `TextMatchHighlight`

* `beginIndice` (Int!): The indice in the fragment where the matched text begins.
* `endIndice` (Int!): The indice in the fragment where the matched text ends.
* `text` (String!): The text matched.