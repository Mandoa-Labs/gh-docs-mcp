# Dependency graph

Reference documentation for GraphQL schema types in the Dependency graph category.

## DependencyGraphDependency - object

A dependency manifest entry.

### Fields for `DependencyGraphDependency`

* `hasDependencies` (Boolean!): Does the dependency itself have dependencies?.
* `packageLabel` (String!): The original name of the package, as it appears in the manifest. **Deprecated:** packageLabel will be removed. Use normalized packageName field instead. Removal on 2022-10-01 UTC.
* `packageManager` (String): The dependency package manager.
* `packageName` (String!): The name of the package in the canonical form used by the package manager.
* `packageUrl` (URI): Public preview: The dependency package URL.
* `relationship` (String!): Public preview: The relationship of the dependency. Can be direct, transitive, or unknown.
* `repository` (Repository): The repository containing the package.
* `requirements` (String!): The dependency version requirements.

## DependencyGraphDependencyConnection - object

The connection type for DependencyGraphDependency.

### Fields for `DependencyGraphDependencyConnection`

* `edges` ([DependencyGraphDependencyEdge]): A list of edges.
* `nodes` ([DependencyGraphDependency]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## DependencyGraphDependencyEdge - object

An edge in a connection.

### Fields for `DependencyGraphDependencyEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (DependencyGraphDependency): The item at the end of the edge.

## DependencyGraphEcosystem - enum

The possible ecosystems of a dependency graph package.

### Values for `DependencyGraphEcosystem`

* `ACTIONS`: GitHub Actions.
* `COMPOSER`: PHP packages hosted at packagist.org.
* `GO`: Go modules.
* `MAVEN`: Java artifacts hosted at the Maven central repository.
* `NPM`: JavaScript packages hosted at npmjs.com.
* `NUGET`: .NET packages hosted at the NuGet Gallery.
* `PIP`: Python packages hosted at PyPI.org.
* `PUB`: Dart packages hosted at pub.dev.
* `RUBYGEMS`: Ruby gems hosted at RubyGems.org.
* `RUST`: Rust crates.
* `SWIFT`: Swift packages.

## DependencyGraphManifest - object

Dependency manifest for a repository.

**Implements:** Node

### Fields for `DependencyGraphManifest`

* `blobPath` (String!): Path to view the manifest file blob.
* `dependencies` (DependencyGraphDependencyConnection): A list of manifest dependencies. _(Pagination: `after`, `before`, `first`, `last`)_
* `dependenciesCount` (Int): The number of dependencies listed in the manifest.
* `exceedsMaxSize` (Boolean!): Is the manifest too big to parse?.
* `filename` (String!): Fully qualified manifest filename.
* `id` (ID!): The Node ID of the DependencyGraphManifest object.
* `parseable` (Boolean!): Were we able to parse the manifest?.
* `repository` (Repository!): The repository containing the manifest.

## DependencyGraphManifestConnection - object

The connection type for DependencyGraphManifest.

### Fields for `DependencyGraphManifestConnection`

* `edges` ([DependencyGraphManifestEdge]): A list of edges.
* `nodes` ([DependencyGraphManifest]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## DependencyGraphManifestEdge - object

An edge in a connection.

### Fields for `DependencyGraphManifestEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (DependencyGraphManifest): The item at the end of the edge.