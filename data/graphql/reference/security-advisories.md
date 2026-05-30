# Security advisories

Reference documentation for GraphQL schema types in the Security advisories category.

## CVSS - object

The Common Vulnerability Scoring System.

### Fields for `CVSS`

* `score` (Float!): The CVSS score associated with this advisory.
* `vectorString` (String): The CVSS vector string associated with this advisory.

## CvssSeverities - object

The Common Vulnerability Scoring System.

### Fields for `CvssSeverities`

* `cvssV3` (CVSS): The CVSS v3 severity associated with this advisory.
* `cvssV4` (CVSS): The CVSS v4 severity associated with this advisory.

## CWE - object

A common weakness enumeration.

**Implements:** Node

### Fields for `CWE`

* `cweId` (String!): The id of the CWE.
* `description` (String!): A detailed description of this CWE.
* `id` (ID!): The Node ID of the CWE object.
* `name` (String!): The name of this CWE.

## CWEConnection - object

The connection type for CWE.

### Fields for `CWEConnection`

* `edges` ([CWEEdge]): A list of edges.
* `nodes` ([CWE]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## CWEEdge - object

An edge in a connection.

### Fields for `CWEEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (CWE): The item at the end of the edge.

## EPSS - object

The Exploit Prediction Scoring System.

### Fields for `EPSS`

* `percentage` (Float): The EPSS percentage represents the likelihood of a CVE being exploited.
* `percentile` (Float): The EPSS percentile represents the relative rank of the CVE's likelihood of being exploited compared to other CVEs.

## securityAdvisories - query

GitHub Security Advisories.

**Type:** SecurityAdvisoryConnection!

### Arguments for `securityAdvisories`

* `after` (String): Returns the elements in the list that come after the specified cursor.
* `before` (String): Returns the elements in the list that come before the specified cursor.
* `classifications` ([SecurityAdvisoryClassification!]): A list of classifications to filter advisories by.
* `epssPercentage` (Float): The EPSS percentage to filter advisories by.
* `epssPercentile` (Float): The EPSS percentile to filter advisories by.
* `first` (Int): Returns the first n elements from the list.
* `identifier` (SecurityAdvisoryIdentifierFilter): Filter advisories by identifier, e.g. GHSA or CVE.
* `last` (Int): Returns the last n elements from the list.
* `orderBy` (SecurityAdvisoryOrder): Ordering options for the returned topics.
* `publishedSince` (DateTime): Filter advisories to those published since a time in the past.
* `updatedSince` (DateTime): Filter advisories to those updated since a time in the past.

## SecurityAdvisory - object

A GitHub Security Advisory.

**Implements:** Node

### Fields for `SecurityAdvisory`

* `classification` (SecurityAdvisoryClassification!): The classification of the advisory.
* `cvss` (CVSS!): The CVSS associated with this advisory. **Deprecated:** cvss will be removed. New cvss_severities field will now contain both cvss_v3 and cvss_v4 properties. Removal on 2025-10-01 UTC.
* `cvssSeverities` (CvssSeverities!): The CVSS associated with this advisory.
* `cwes` (CWEConnection!): CWEs associated with this Advisory. _(Pagination: `after`, `before`, `first`, `last`)_
* `databaseId` (Int): Identifies the primary key from the database.
* `description` (String!): This is a long plaintext description of the advisory.
* `epss` (EPSS): The Exploit Prediction Scoring System.
* `ghsaId` (String!): The GitHub Security Advisory ID.
* `id` (ID!): The Node ID of the SecurityAdvisory object.
* `identifiers` ([SecurityAdvisoryIdentifier!]!): A list of identifiers for this advisory.
* `notificationsPermalink` (URI): The permalink for the advisory's dependabot alerts page.
* `origin` (String!): The organization that originated the advisory.
* `permalink` (URI): The permalink for the advisory.
* `publishedAt` (DateTime!): When the advisory was published.
* `references` ([SecurityAdvisoryReference!]!): A list of references for this advisory.
* `severity` (SecurityAdvisorySeverity!): The severity of the advisory.
* `summary` (String!): A short plaintext summary of the advisory.
* `updatedAt` (DateTime!): When the advisory was last updated.
* `vulnerabilities` (SecurityVulnerabilityConnection!): Vulnerabilities associated with this Advisory.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `classifications` ([SecurityAdvisoryClassification!]): A list of advisory classifications to filter vulnerabilities by.
  * `ecosystem` (SecurityAdvisoryEcosystem): An ecosystem to filter vulnerabilities by.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (SecurityVulnerabilityOrder): Ordering options for the returned topics.
  * `package` (String): A package name to filter vulnerabilities by.
  * `severities` ([SecurityAdvisorySeverity!]): A list of severities to filter vulnerabilities by.

* `withdrawnAt` (DateTime): When the advisory was withdrawn, if it has been withdrawn.

## securityAdvisory - query

Fetch a Security Advisory by its GHSA ID.

**Type:** SecurityAdvisory

### Arguments for `securityAdvisory`

* `ghsaId` (String!): GitHub Security Advisory ID.

## SecurityAdvisoryClassification - enum

Classification of the advisory.

### Values for `SecurityAdvisoryClassification`

* `GENERAL`: Classification of general advisories.
* `MALWARE`: Classification of malware advisories.

## SecurityAdvisoryConnection - object

The connection type for SecurityAdvisory.

### Fields for `SecurityAdvisoryConnection`

* `edges` ([SecurityAdvisoryEdge]): A list of edges.
* `nodes` ([SecurityAdvisory]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## SecurityAdvisoryEcosystem - enum

The possible ecosystems of a security vulnerability's package.

### Values for `SecurityAdvisoryEcosystem`

* `ACTIONS`: GitHub Actions.
* `COMPOSER`: PHP packages hosted at packagist.org.
* `ERLANG`: Erlang/Elixir packages hosted at hex.pm.
* `GO`: Go modules.
* `MAVEN`: Java artifacts hosted at the Maven central repository.
* `NPM`: JavaScript packages hosted at npmjs.com.
* `NUGET`: .NET packages hosted at the NuGet Gallery.
* `PIP`: Python packages hosted at PyPI.org.
* `PUB`: Dart packages hosted at pub.dev.
* `RUBYGEMS`: Ruby gems hosted at RubyGems.org.
* `RUST`: Rust crates.
* `SWIFT`: Swift packages.

## SecurityAdvisoryEdge - object

An edge in a connection.

### Fields for `SecurityAdvisoryEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (SecurityAdvisory): The item at the end of the edge.

## SecurityAdvisoryIdentifier - object

A GitHub Security Advisory Identifier.

### Fields for `SecurityAdvisoryIdentifier`

* `type` (String!): The identifier type, e.g. GHSA, CVE.
* `value` (String!): The identifier.

## SecurityAdvisoryIdentifierFilter - input object

An advisory identifier to filter results on.

### Input fields for `SecurityAdvisoryIdentifierFilter`

* `type` (SecurityAdvisoryIdentifierType!): The identifier type.
* `value` (String!): The identifier string. Supports exact or partial matching.

## SecurityAdvisoryIdentifierType - enum

Identifier formats available for advisories.

### Values for `SecurityAdvisoryIdentifierType`

* `CVE`: Common Vulnerabilities and Exposures Identifier.
* `GHSA`: GitHub Security Advisory ID.

## SecurityAdvisoryOrder - input object

Ordering options for security advisory connections.

### Input fields for `SecurityAdvisoryOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (SecurityAdvisoryOrderField!): The field to order security advisories by.

## SecurityAdvisoryOrderField - enum

Properties by which security advisory connections can be ordered.

### Values for `SecurityAdvisoryOrderField`

* `EPSS_PERCENTAGE`: Order advisories by EPSS percentage.
* `EPSS_PERCENTILE`: Order advisories by EPSS percentile.
* `PUBLISHED_AT`: Order advisories by publication time.
* `UPDATED_AT`: Order advisories by update time.

## SecurityAdvisoryPackage - object

An individual package.

### Fields for `SecurityAdvisoryPackage`

* `ecosystem` (SecurityAdvisoryEcosystem!): The ecosystem the package belongs to, e.g. RUBYGEMS, NPM.
* `name` (String!): The package name.

## SecurityAdvisoryPackageVersion - object

An individual package version.

### Fields for `SecurityAdvisoryPackageVersion`

* `identifier` (String!): The package name or version.

## SecurityAdvisoryReference - object

A GitHub Security Advisory Reference.

### Fields for `SecurityAdvisoryReference`

* `url` (URI!): A publicly accessible reference.

## SecurityAdvisorySeverity - enum

Severity of the vulnerability.

### Values for `SecurityAdvisorySeverity`

* `CRITICAL`: Critical.
* `HIGH`: High.
* `LOW`: Low.
* `MODERATE`: Moderate.
* `UNKNOWN`: Unknown.

## securityVulnerabilities - query

Software Vulnerabilities documented by GitHub Security Advisories.

**Type:** SecurityVulnerabilityConnection!

### Arguments for `securityVulnerabilities`

* `after` (String): Returns the elements in the list that come after the specified cursor.
* `before` (String): Returns the elements in the list that come before the specified cursor.
* `classifications` ([SecurityAdvisoryClassification!]): A list of advisory classifications to filter vulnerabilities by.
* `ecosystem` (SecurityAdvisoryEcosystem): An ecosystem to filter vulnerabilities by.
* `first` (Int): Returns the first n elements from the list.
* `last` (Int): Returns the last n elements from the list.
* `orderBy` (SecurityVulnerabilityOrder): Ordering options for the returned topics.
* `package` (String): A package name to filter vulnerabilities by.
* `severities` ([SecurityAdvisorySeverity!]): A list of severities to filter vulnerabilities by.

## SecurityVulnerability - object

An individual vulnerability within an Advisory.

### Fields for `SecurityVulnerability`

* `advisory` (SecurityAdvisory!): The Advisory associated with this Vulnerability.
* `firstPatchedVersion` (SecurityAdvisoryPackageVersion): The first version containing a fix for the vulnerability.
* `package` (SecurityAdvisoryPackage!): A description of the vulnerable package.
* `severity` (SecurityAdvisorySeverity!): The severity of the vulnerability within this package.
* `updatedAt` (DateTime!): When the vulnerability was last updated.
* `vulnerableVersionRange` (String!): A string that describes the vulnerable package versions.
This string follows a basic syntax with a few forms.

= 0.2.0 denotes a single vulnerable version.
<= 1.0.8 denotes a version range up to and including the specified version
< 0.1.11 denotes a version range up to, but excluding, the specified version
>= 4.3.0, < 4.3.5 denotes a version range with a known minimum and maximum version.
>= 0.0.1 denotes a version range with a known minimum, but no known maximum.

## SecurityVulnerabilityConnection - object

The connection type for SecurityVulnerability.

### Fields for `SecurityVulnerabilityConnection`

* `edges` ([SecurityVulnerabilityEdge]): A list of edges.
* `nodes` ([SecurityVulnerability]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## SecurityVulnerabilityEdge - object

An edge in a connection.

### Fields for `SecurityVulnerabilityEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (SecurityVulnerability): The item at the end of the edge.

## SecurityVulnerabilityOrder - input object

Ordering options for security vulnerability connections.

### Input fields for `SecurityVulnerabilityOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (SecurityVulnerabilityOrderField!): The field to order security vulnerabilities by.

## SecurityVulnerabilityOrderField - enum

Properties by which security vulnerability connections can be ordered.

### Values for `SecurityVulnerabilityOrderField`

* `UPDATED_AT`: Order vulnerability by update time.