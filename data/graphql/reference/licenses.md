# Licenses

Reference documentation for GraphQL schema types in the Licenses category.

## License - object

A repository's open source license.

**Implements:** Node

### Fields for `License`

* `body` (String!): The full text of the license.
* `conditions` ([LicenseRule]!): The conditions set by the license.
* `description` (String): A human-readable description of the license.
* `featured` (Boolean!): Whether the license should be featured.
* `hidden` (Boolean!): Whether the license should be displayed in license pickers.
* `id` (ID!): The Node ID of the License object.
* `implementation` (String): Instructions on how to implement the license.
* `key` (String!): The lowercased SPDX ID of the license.
* `limitations` ([LicenseRule]!): The limitations set by the license.
* `name` (String!): The license full name specified by https://spdx.org/licenses.
* `nickname` (String): Customary short name if applicable (e.g, GPLv3).
* `permissions` ([LicenseRule]!): The permissions set by the license.
* `pseudoLicense` (Boolean!): Whether the license is a pseudo-license placeholder (e.g., other, no-license).
* `spdxId` (String): Short identifier specified by https://spdx.org/licenses.
* `url` (URI): URL to the license on https://choosealicense.com.

## license - query

Look up an open source license by its key.

**Type:** License

### Arguments for `license`

* `key` (String!): The license's downcased SPDX ID.

## LicenseRule - object

Describes a License's conditions, permissions, and limitations.

### Fields for `LicenseRule`

* `description` (String!): A description of the rule.
* `key` (String!): The machine-readable rule key.
* `label` (String!): The human-readable rule label.

## licenses - query

Return a list of known open source licenses.

**Type:** [License]!