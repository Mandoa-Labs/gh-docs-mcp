# Meta

Reference documentation for GraphQL schema types in the Meta category.

## CodeOfConduct - object

The Code of Conduct for a repository.

**Implements:** Node

### Fields for `CodeOfConduct`

* `body` (String): The body of the Code of Conduct.
* `id` (ID!): The Node ID of the CodeOfConduct object.
* `key` (String!): The key for the Code of Conduct.
* `name` (String!): The formal name of the Code of Conduct.
* `resourcePath` (URI): The HTTP path for this Code of Conduct.
* `url` (URI): The HTTP URL for this Code of Conduct.

## codeOfConduct - query

Look up a code of conduct by its key.

**Type:** CodeOfConduct

### Arguments for `codeOfConduct`

* `key` (String!): The code of conduct's key.

## codesOfConduct - query

Look up a code of conduct by its key.

**Type:** [CodeOfConduct]

## ContentWarning - object

The content warning for a repository.

### Fields for `ContentWarning`

* `category` (String!): The content warning' category. E.g. 'mis_dis_information'.
* `customSubCategory` (String): The content warning's custom sub category text. E.g. 'dangerous stuff.'.
* `subCategory` (String): The content warning's sub category. E.g. 'medical_scientific'.
* `subTitle` (String): The content warning's sub title. E.g. 'The information contained in this page has not been verified.'.
* `title` (String!): The content warning's title. E.g. 'This page may contain false or misleading information.'.
* `type` (String!): The type of content warning. E.g. 'interstitial'.

## GitHubMetadata - object

Represents information about the GitHub instance.

### Fields for `GitHubMetadata`

* `gitHubServicesSha` (GitObjectID!): Returns a String that's a SHA of github-services.
* `gitIpAddresses` ([String!]): IP addresses that users connect to for git operations.
* `githubEnterpriseImporterIpAddresses` ([String!]): IP addresses that GitHub Enterprise Importer uses for outbound connections.
* `hookIpAddresses` ([String!]): IP addresses that service hooks are sent from.
* `importerIpAddresses` ([String!]): IP addresses that the importer connects from.
* `isPasswordAuthenticationVerifiable` (Boolean!): Whether or not users are verified.
* `pagesIpAddresses` ([String!]): IP addresses for GitHub Pages' A records.

## meta - query

Return information about the GitHub instance.

**Type:** GitHubMetadata!

## Node - interface

An object with an ID.

### Fields for `Node`

* `id` (ID!): ID of the object.

### Implemented by

* Workflow
* WorkflowRun
* WorkflowRunFile
* App
* Bot
* MarketplaceCategory
* MarketplaceListing
* BranchProtectionRule
* BypassForcePushAllowance
* BypassPullRequestAllowance
* PushAllowance
* ReviewDismissalAllowance
* CheckRun
* CheckSuite
* Commit
* CommitComment
* CommitCommentThread
* Comparison
* Status
* StatusCheckRollup
* StatusContext
* RepositoryVulnerabilityAlert
* DependencyGraphManifest
* DeployKey
* DeployedEvent
* Deployment
* DeploymentEnvironmentChangedEvent
* DeploymentReview
* DeploymentStatus
* Environment
* PinnedEnvironment
* Discussion
* DiscussionCategory
* DiscussionComment
* DiscussionPoll
* DiscussionPollOption
* PinnedDiscussion
* Enterprise
* EnterpriseAdministratorInvitation
* EnterpriseIdentityProvider
* EnterpriseMemberInvitation
* EnterpriseRepositoryInfo
* EnterpriseServerInstallation
* EnterpriseServerUserAccount
* EnterpriseServerUserAccountEmail
* EnterpriseServerUserAccountsUpload
* EnterpriseTeam
* EnterpriseUserAccount
* ExternalIdentity
* IpAllowListEntry
* MembersCanDeleteReposClearAuditEntry
* MembersCanDeleteReposDisableAuditEntry
* MembersCanDeleteReposEnableAuditEntry
* OIDCProvider
* OauthApplicationCreateAuditEntry
* PrivateRepositoryForkingDisableAuditEntry
* PrivateRepositoryForkingEnableAuditEntry
* RepoConfigDisableAnonymousGitAccessAuditEntry
* RepoConfigDisableCollaboratorsOnlyAuditEntry
* RepoConfigDisableContributorsOnlyAuditEntry
* RepoConfigDisableSockpuppetDisallowedAuditEntry
* RepoConfigEnableAnonymousGitAccessAuditEntry
* RepoConfigEnableCollaboratorsOnlyAuditEntry
* RepoConfigEnableContributorsOnlyAuditEntry
* RepoConfigEnableSockpuppetDisallowedAuditEntry
* RepoConfigLockAnonymousGitAccessAuditEntry
* RepoConfigUnlockAnonymousGitAccessAuditEntry
* RepositoryVisibilityChangeDisableAuditEntry
* RepositoryVisibilityChangeEnableAuditEntry
* UserNamespaceRepository
* Gist
* GistComment
* Blob
* Push
* Ref
* Tag
* Tree
* AssignedEvent
* BlockedByAddedEvent
* BlockedByRemovedEvent
* BlockingAddedEvent
* BlockingRemovedEvent
* ClosedEvent
* CommentDeletedEvent
* ConnectedEvent
* ConvertedNoteToIssueEvent
* ConvertedToDiscussionEvent
* CrossReferencedEvent
* DemilestonedEvent
* DisconnectedEvent
* Issue
* IssueComment
* IssueCommentPinnedEvent
* IssueCommentUnpinnedEvent
* IssueFieldAddedEvent
* IssueFieldChangedEvent
* IssueFieldDate
* IssueFieldDateValue
* IssueFieldNumber
* IssueFieldNumberValue
* IssueFieldRemovedEvent
* IssueFieldSingleSelect
* IssueFieldSingleSelectOption
* IssueFieldSingleSelectValue
* IssueFieldText
* IssueFieldTextValue
* IssueType
* IssueTypeAddedEvent
* IssueTypeChangedEvent
* IssueTypeRemovedEvent
* Label
* LabeledEvent
* LinkedBranch
* LockedEvent
* MarkedAsDuplicateEvent
* MentionedEvent
* Milestone
* MilestonedEvent
* ParentIssueAddedEvent
* ParentIssueRemovedEvent
* PinnedEvent
* PinnedIssue
* PinnedIssueComment
* ReferencedEvent
* RenamedTitleEvent
* ReopenedEvent
* SubIssueAddedEvent
* SubIssueRemovedEvent
* SubscribedEvent
* TransferredEvent
* UnassignedEvent
* UnlabeledEvent
* UnlockedEvent
* UnmarkedAsDuplicateEvent
* UnpinnedEvent
* UnsubscribedEvent
* License
* CodeOfConduct
* Mannequin
* MigrationSource
* OrganizationMigration
* RepositoryMigration
* MemberFeatureRequestNotification
* OrgAddBillingManagerAuditEntry
* OrgAddMemberAuditEntry
* OrgBlockUserAuditEntry
* OrgConfigDisableCollaboratorsOnlyAuditEntry
* OrgConfigEnableCollaboratorsOnlyAuditEntry
* OrgCreateAuditEntry
* OrgDisableOauthAppRestrictionsAuditEntry
* OrgDisableSamlAuditEntry
* OrgDisableTwoFactorRequirementAuditEntry
* OrgEnableOauthAppRestrictionsAuditEntry
* OrgEnableSamlAuditEntry
* OrgEnableTwoFactorRequirementAuditEntry
* OrgInviteMemberAuditEntry
* OrgInviteToBusinessAuditEntry
* OrgOauthAppAccessApprovedAuditEntry
* OrgOauthAppAccessBlockedAuditEntry
* OrgOauthAppAccessDeniedAuditEntry
* OrgOauthAppAccessRequestedAuditEntry
* OrgOauthAppAccessUnblockedAuditEntry
* OrgRemoveBillingManagerAuditEntry
* OrgRemoveMemberAuditEntry
* OrgRemoveOutsideCollaboratorAuditEntry
* OrgRestoreMemberAuditEntry
* OrgUnblockUserAuditEntry
* OrgUpdateDefaultRepositoryPermissionAuditEntry
* OrgUpdateMemberAuditEntry
* OrgUpdateMemberRepositoryCreationPermissionAuditEntry
* OrgUpdateMemberRepositoryInvitationPermissionAuditEntry
* Organization
* OrganizationIdentityProvider
* OrganizationInvitation
* VerifiableDomain
* Package
* PackageFile
* PackageTag
* PackageVersion
* AddedToProjectV2Event
* DraftIssue
* ProjectV2
* ProjectV2Field
* ProjectV2Item
* ProjectV2ItemFieldDateValue
* ProjectV2ItemFieldIterationValue
* ProjectV2ItemFieldNumberValue
* ProjectV2ItemFieldSingleSelectValue
* ProjectV2ItemFieldTextValue
* ProjectV2ItemStatusChangedEvent
* ProjectV2IterationField
* ProjectV2SingleSelectField
* ProjectV2StatusUpdate
* ProjectV2View
* ProjectV2Workflow
* RemovedFromProjectV2Event
* AddedToProjectEvent
* MovedColumnsInProjectEvent
* Project
* ProjectCard
* ProjectColumn
* RemovedFromProjectEvent
* AddedToMergeQueueEvent
* AutoMergeDisabledEvent
* AutoMergeEnabledEvent
* AutoRebaseEnabledEvent
* AutoSquashEnabledEvent
* AutomaticBaseChangeFailedEvent
* AutomaticBaseChangeSucceededEvent
* BaseRefChangedEvent
* BaseRefDeletedEvent
* BaseRefForcePushedEvent
* ConvertToDraftEvent
* ConvertedFromDraftEvent
* HeadRefDeletedEvent
* HeadRefForcePushedEvent
* HeadRefRestoredEvent
* MergeQueue
* MergeQueueEntry
* MergedEvent
* PullRequest
* PullRequestCommit
* PullRequestCommitCommentThread
* PullRequestReview
* PullRequestReviewComment
* PullRequestReviewThread
* PullRequestThread
* ReadyForReviewEvent
* RemovedFromMergeQueueEvent
* ReviewDismissedEvent
* ReviewRequest
* ReviewRequestRemovedEvent
* ReviewRequestedEvent
* Reaction
* Release
* ReleaseAsset
* Language
* RepoAccessAuditEntry
* RepoAddMemberAuditEntry
* RepoAddTopicAuditEntry
* RepoArchivedAuditEntry
* RepoChangeMergeSettingAuditEntry
* RepoCreateAuditEntry
* RepoDestroyAuditEntry
* RepoRemoveMemberAuditEntry
* RepoRemoveTopicAuditEntry
* Repository
* RepositoryCustomProperty
* RepositoryInvitation
* RepositoryRule
* RepositoryRuleset
* RepositoryRulesetBypassActor
* RepositoryTopic
* Topic
* CWE
* SecurityAdvisory
* SponsorsActivity
* SponsorsListing
* SponsorsListingFeaturedItem
* SponsorsTier
* Sponsorship
* SponsorshipNewsletter
* Team
* TeamAddMemberAuditEntry
* TeamAddRepositoryAuditEntry
* TeamChangeParentTeamAuditEntry
* TeamRemoveMemberAuditEntry
* TeamRemoveRepositoryAuditEntry
* PublicKey
* SavedReply
* User
* UserBlockedEvent
* UserContentEdit
* UserList
* UserStatus

## node - query

Fetches an object given its ID.

**Type:** Node

### Arguments for `node`

* `id` (ID!): ID of the object.

## nodes - query

Lookup nodes by a list of IDs.

**Type:** [Node]!

### Arguments for `nodes`

* `ids` ([ID!]!): The list of node IDs.

## OperationType - enum

The corresponding operation type for the action.

### Values for `OperationType`

* `ACCESS`: An existing resource was accessed.
* `AUTHENTICATION`: A resource performed an authentication event.
* `CREATE`: A new resource was created.
* `MODIFY`: An existing resource was modified.
* `REMOVE`: An existing resource was removed.
* `RESTORE`: An existing resource was restored.
* `TRANSFER`: An existing resource was transferred between multiple resources.

## OrderDirection - enum

Possible directions in which to order a list of items when provided an orderBy argument.

### Values for `OrderDirection`

* `ASC`: Specifies an ascending order for a given orderBy argument.
* `DESC`: Specifies a descending order for a given orderBy argument.

## RateLimit - object

Represents the client's rate limit.

### Fields for `RateLimit`

* `cost` (Int!): The point cost for the current query counting against the rate limit.
* `limit` (Int!): The maximum number of points the client is permitted to consume in a 60 minute window.
* `nodeCount` (Int!): The maximum number of nodes this query may return.
* `remaining` (Int!): The number of points remaining in the current rate limit window.
* `resetAt` (DateTime!): The time at which the current rate limit window resets in UTC epoch seconds.
* `used` (Int!): The number of points used in the current rate limit window.

## rateLimit - query

The client's rate limit information.

**Type:** RateLimit

### Arguments for `rateLimit`

* `dryRun` (Boolean): If true, calculate the cost for the query without evaluating it.

## ReportedContentClassifiers - enum

The reasons a piece of content can be reported or minimized.

### Values for `ReportedContentClassifiers`

* `ABUSE`: An abusive or harassing piece of content.
* `DUPLICATE`: A duplicated piece of content.
* `LOW_QUALITY`: A low quality piece of content.
* `OFF_TOPIC`: An irrelevant piece of content.
* `OUTDATED`: An outdated piece of content.
* `RESOLVED`: The content has been resolved.
* `SPAM`: A spammy piece of content.

## resource - query

Lookup resource by a URL.

**Type:** UniformResourceLocatable

### Arguments for `resource`

* `url` (URI!): The URL.

## UniformResourceLocatable - interface

Represents a type that can be retrieved by a URL.

### Fields for `UniformResourceLocatable`

* `resourcePath` (URI!): The HTML path to this resource.
* `url` (URI!): The URL to this resource.

### Implemented by

* Workflow
* WorkflowRun
* WorkflowRunFile
* Bot
* CheckRun
* Commit
* Gist
* ClosedEvent
* CrossReferencedEvent
* Issue
* Milestone
* Mannequin
* Organization
* ConvertToDraftEvent
* MergedEvent
* PullRequest
* PullRequestCommit
* ReadyForReviewEvent
* ReviewDismissedEvent
* Release
* Repository
* RepositoryTopic
* User