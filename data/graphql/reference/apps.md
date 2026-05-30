# GitHub Apps

Reference documentation for GraphQL schema types in the GitHub Apps category.

## App - object

A GitHub App.

**Implements:** Node

### Fields for `App`

* `clientId` (String): The client ID of the app.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `description` (String): The description of the app.
* `id` (ID!): The Node ID of the App object.
* `ipAllowListEntries` (IpAllowListEntryConnection!): The IP addresses of the app.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (IpAllowListEntryOrder): Ordering options for IP allow list entries returned.

* `logoBackgroundColor` (String!): The hex color code, without the leading '#', for the logo background.
* `logoUrl` (URI!): A URL pointing to the app's logo.
  * `size` (Int): The size of the resulting image.

* `name` (String!): The name of the app.
* `slug` (String!): A slug based on the name of the app for use in URLs.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The URL to the app's homepage.

## Bot - object

A special type of user which takes actions on behalf of GitHub Apps.

**Implements:** Actor, Node, UniformResourceLocatable

### Fields for `Bot`

* `avatarUrl` (URI!): A URL pointing to the GitHub App's public avatar.
  * `size` (Int): The size of the resulting square image.

* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `id` (ID!): The Node ID of the Bot object.
* `login` (String!): The username of the actor.
* `resourcePath` (URI!): The HTTP path for this bot.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this bot.

## marketplaceCategories - query

Get alphabetically sorted list of Marketplace categories.

**Type:** [MarketplaceCategory!]!

### Arguments for `marketplaceCategories`

* `excludeEmpty` (Boolean): Exclude categories with no listings.
* `excludeSubcategories` (Boolean): Returns top level categories only, excluding any subcategories.
* `includeCategories` ([String!]): Return only the specified categories.

## MarketplaceCategory - object

A public description of a Marketplace category.

**Implements:** Node

### Fields for `MarketplaceCategory`

* `description` (String): The category's description.
* `howItWorks` (String): The technical description of how apps listed in this category work with GitHub.
* `id` (ID!): The Node ID of the MarketplaceCategory object.
* `name` (String!): The category's name.
* `primaryListingCount` (Int!): How many Marketplace listings have this as their primary category.
* `resourcePath` (URI!): The HTTP path for this Marketplace category.
* `secondaryListingCount` (Int!): How many Marketplace listings have this as their secondary category.
* `slug` (String!): The short name of the category used in its URL.
* `url` (URI!): The HTTP URL for this Marketplace category.

## marketplaceCategory - query

Look up a Marketplace category by its slug.

**Type:** MarketplaceCategory

### Arguments for `marketplaceCategory`

* `slug` (String!): The URL slug of the category.
* `useTopicAliases` (Boolean): Also check topic aliases for the category slug.

## MarketplaceListing - object

A listing in the GitHub integration marketplace.

**Implements:** Node

### Fields for `MarketplaceListing`

* `app` (App): The GitHub App this listing represents.
* `companyUrl` (URI): URL to the listing owner's company site.
* `configurationResourcePath` (URI!): The HTTP path for configuring access to the listing's integration or OAuth app.
* `configurationUrl` (URI!): The HTTP URL for configuring access to the listing's integration or OAuth app.
* `documentationUrl` (URI): URL to the listing's documentation.
* `extendedDescription` (String): The listing's detailed description.
* `extendedDescriptionHTML` (HTML!): The listing's detailed description rendered to HTML.
* `fullDescription` (String!): The listing's introductory description.
* `fullDescriptionHTML` (HTML!): The listing's introductory description rendered to HTML.
* `hasPublishedFreeTrialPlans` (Boolean!): Does this listing have any plans with a free trial?.
* `hasTermsOfService` (Boolean!): Does this listing have a terms of service link?.
* `hasVerifiedOwner` (Boolean!): Whether the creator of the app is a verified org.
* `howItWorks` (String): A technical description of how this app works with GitHub.
* `howItWorksHTML` (HTML!): The listing's technical description rendered to HTML.
* `id` (ID!): The Node ID of the MarketplaceListing object.
* `installationUrl` (URI): URL to install the product to the viewer's account or organization.
* `installedForViewer` (Boolean!): Whether this listing's app has been installed for the current viewer.
* `isArchived` (Boolean!): Whether this listing has been removed from the Marketplace.
* `isDraft` (Boolean!): Whether this listing is still an editable draft that has not been submitted
for review and is not publicly visible in the Marketplace.
* `isPaid` (Boolean!): Whether the product this listing represents is available as part of a paid plan.
* `isPublic` (Boolean!): Whether this listing has been approved for display in the Marketplace.
* `isRejected` (Boolean!): Whether this listing has been rejected by GitHub for display in the Marketplace.
* `isUnverified` (Boolean!): Whether this listing has been approved for unverified display in the Marketplace.
* `isUnverifiedPending` (Boolean!): Whether this draft listing has been submitted for review for approval to be unverified in the Marketplace.
* `isVerificationPendingFromDraft` (Boolean!): Whether this draft listing has been submitted for review from GitHub for approval to be verified in the Marketplace.
* `isVerificationPendingFromUnverified` (Boolean!): Whether this unverified listing has been submitted for review from GitHub for approval to be verified in the Marketplace.
* `isVerified` (Boolean!): Whether this listing has been approved for verified display in the Marketplace.
* `logoBackgroundColor` (String!): The hex color code, without the leading '#', for the logo background.
* `logoUrl` (URI): URL for the listing's logo image.
  * `size` (Int): The size in pixels of the resulting square image. Default: `400`.

* `name` (String!): The listing's full name.
* `normalizedShortDescription` (String!): The listing's very short description without a trailing period or ampersands.
* `pricingUrl` (URI): URL to the listing's detailed pricing.
* `primaryCategory` (MarketplaceCategory!): The category that best describes the listing.
* `privacyPolicyUrl` (URI!): URL to the listing's privacy policy, may return an empty string for listings that do not require a privacy policy URL.
* `resourcePath` (URI!): The HTTP path for the Marketplace listing.
* `screenshotUrls` ([String]!): The URLs for the listing's screenshots.
* `secondaryCategory` (MarketplaceCategory): An alternate category that describes the listing.
* `shortDescription` (String!): The listing's very short description.
* `slug` (String!): The short name of the listing used in its URL.
* `statusUrl` (URI): URL to the listing's status page.
* `supportEmail` (String): An email address for support for this listing's app.
* `supportUrl` (URI!): Either a URL or an email address for support for this listing's app, may
return an empty string for listings that do not require a support URL.
* `termsOfServiceUrl` (URI): URL to the listing's terms of service.
* `url` (URI!): The HTTP URL for the Marketplace listing.
* `viewerCanAddPlans` (Boolean!): Can the current viewer add plans for this Marketplace listing.
* `viewerCanApprove` (Boolean!): Can the current viewer approve this Marketplace listing.
* `viewerCanDelist` (Boolean!): Can the current viewer delist this Marketplace listing.
* `viewerCanEdit` (Boolean!): Can the current viewer edit this Marketplace listing.
* `viewerCanEditCategories` (Boolean!): Can the current viewer edit the primary and secondary category of this
Marketplace listing.
* `viewerCanEditPlans` (Boolean!): Can the current viewer edit the plans for this Marketplace listing.
* `viewerCanRedraft` (Boolean!): Can the current viewer return this Marketplace listing to draft state
so it becomes editable again.
* `viewerCanReject` (Boolean!): Can the current viewer reject this Marketplace listing by returning it to
an editable draft state or rejecting it entirely.
* `viewerCanRequestApproval` (Boolean!): Can the current viewer request this listing be reviewed for display in
the Marketplace as verified.
* `viewerHasPurchased` (Boolean!): Indicates whether the current user has an active subscription to this Marketplace listing.
* `viewerHasPurchasedForAllOrganizations` (Boolean!): Indicates if the current user has purchased a subscription to this Marketplace listing
for all of the organizations the user owns.
* `viewerIsListingAdmin` (Boolean!): Does the current viewer role allow them to administer this Marketplace listing.

## marketplaceListing - query

Look up a single Marketplace listing.

**Type:** MarketplaceListing

### Arguments for `marketplaceListing`

* `slug` (String!): Select the listing that matches this slug. It's the short name of the listing used in its URL.

## MarketplaceListingConnection - object

Look up Marketplace Listings.

### Fields for `MarketplaceListingConnection`

* `edges` ([MarketplaceListingEdge]): A list of edges.
* `nodes` ([MarketplaceListing]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## MarketplaceListingEdge - object

An edge in a connection.

### Fields for `MarketplaceListingEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (MarketplaceListing): The item at the end of the edge.

## marketplaceListings - query

Look up Marketplace listings.

**Type:** MarketplaceListingConnection!

### Arguments for `marketplaceListings`

* `adminId` (ID): Select listings that can be administered by the specified user.
* `after` (String): Returns the elements in the list that come after the specified cursor.
* `allStates` (Boolean): Select listings visible to the viewer even if they are not approved. If omitted or
false, only approved listings will be returned.
* `before` (String): Returns the elements in the list that come before the specified cursor.
* `categorySlug` (String): Select only listings with the given category.
* `first` (Int): Returns the first n elements from the list.
* `last` (Int): Returns the last n elements from the list.
* `organizationId` (ID): Select listings for products owned by the specified organization.
* `primaryCategoryOnly` (Boolean): Select only listings where the primary category matches the given category slug.
* `slugs` ([String]): Select the listings with these slugs, if they are visible to the viewer.
* `useTopicAliases` (Boolean): Also check topic aliases for the category slug.
* `viewerCanAdmin` (Boolean): Select listings to which user has admin access. If omitted, listings visible to the
viewer are returned.
* `withFreeTrialsOnly` (Boolean): Select only listings that offer a free trial.

## OauthApplicationAuditEntryData - interface

Metadata for an audit entry with action oauth_application.*.

### Fields for `OauthApplicationAuditEntryData`

* `oauthApplicationName` (String): The name of the OAuth application.
* `oauthApplicationResourcePath` (URI): The HTTP path for the OAuth application.
* `oauthApplicationUrl` (URI): The HTTP URL for the OAuth application.

### Implemented by

* OauthApplicationCreateAuditEntry
* OrgOauthAppAccessApprovedAuditEntry
* OrgOauthAppAccessBlockedAuditEntry
* OrgOauthAppAccessDeniedAuditEntry
* OrgOauthAppAccessRequestedAuditEntry
* OrgOauthAppAccessUnblockedAuditEntry

## OauthApplicationCreateAuditEntryState - enum

The state of an OAuth application when it was created.

### Values for `OauthApplicationCreateAuditEntryState`

* `ACTIVE`: The OAuth application was active and allowed to have OAuth Accesses.
* `PENDING_DELETION`: The OAuth application was in the process of being deleted.
* `SUSPENDED`: The OAuth application was suspended from generating OAuth Accesses due to abuse or security concerns.