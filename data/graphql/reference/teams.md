# Teams

Reference documentation for GraphQL schema types in the Teams category.

## OrganizationTeamsHovercardContext - object

An organization teams hovercard context.

**Implements:** HovercardContext

### Fields for `OrganizationTeamsHovercardContext`

* `message` (String!): A string describing this context.
* `octicon` (String!): An octicon to accompany this context.
* `relevantTeams` (TeamConnection!): Teams in this organization the user is a member of that are relevant. _(Pagination: `after`, `before`, `first`, `last`)_
* `teamsResourcePath` (URI!): The path for the full team list for this user.
* `teamsUrl` (URI!): The URL for the full team list for this user.
* `totalTeamCount` (Int!): The total number of teams the user is on in the organization.

## Team - object

A team of users in an organization.

**Implements:** MemberStatusable, Node, Subscribable, TeamReviewRequestable

### Fields for `Team`

* `ancestors` (TeamConnection!): A list of teams that are ancestors of this team. _(Pagination: `after`, `before`, `first`, `last`)_
* `avatarUrl` (URI): A URL pointing to the team's avatar.
  * `size` (Int): The size in pixels of the resulting square image. Default: `400`.

* `childTeams` (TeamConnection!): List of child teams belonging to this team.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `immediateOnly` (Boolean): Whether to list immediate child teams or all descendant child teams. Default: `true`.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (TeamOrder): Order for connection.
  * `userLogins` ([String!]): User logins to filter by.

* `combinedSlug` (String!): The slug corresponding to the organization and team.
* `createdAt` (DateTime!): Identifies the date and time when the object was created.
* `databaseId` (Int): Identifies the primary key from the database.
* `description` (String): The description of the team.
* `editTeamResourcePath` (URI!): The HTTP path for editing this team.
* `editTeamUrl` (URI!): The HTTP URL for editing this team.
* `id` (ID!): The Node ID of the Team object.
* `invitations` (OrganizationInvitationConnection): A list of pending invitations for users to this team. _(Pagination: `after`, `before`, `first`, `last`)_
* `memberStatuses` (UserStatusConnection!): Get the status messages members of this entity have set that are either public or visible only to the organization.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (UserStatusOrder): Ordering options for user statuses returned from the connection.

* `members` (TeamMemberConnection!): A list of users who are members of this team.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `membership` (TeamMembershipType): Filter by membership type. Default: `ALL`.
  * `orderBy` (TeamMemberOrder): Order for the connection.
  * `query` (String): The search string to look for.
  * `role` (TeamMemberRole): Filter by team member role.

* `membersResourcePath` (URI!): The HTTP path for the team' members.
* `membersUrl` (URI!): The HTTP URL for the team' members.
* `name` (String!): The name of the team.
* `newTeamResourcePath` (URI!): The HTTP path creating a new team.
* `newTeamUrl` (URI!): The HTTP URL creating a new team.
* `notificationSetting` (TeamNotificationSetting!): The notification setting that the team has set.
* `organization` (Organization!): The organization that owns this team.
* `parentTeam` (Team): The parent team of the team.
* `privacy` (TeamPrivacy!): The level of privacy the team has.
* `projectV2` (ProjectV2): Finds and returns the project according to the provided project number.
  * `number` (Int!): The Project number.

* `projectsV2` (ProjectV2Connection!): List of projects this team has collaborator access to.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `filterBy` (ProjectV2Filters): Filtering options for projects returned from this connection.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `minPermissionLevel` (ProjectV2PermissionLevel): Filter projects based on user role. Default: `READ`.
  * `orderBy` (ProjectV2Order): How to order the returned projects.
  * `query` (String): The query to search projects by. Default: ``.

* `repositories` (TeamRepositoryConnection!): A list of repositories this team has access to.
  * `after` (String): Returns the elements in the list that come after the specified cursor.
  * `before` (String): Returns the elements in the list that come before the specified cursor.
  * `first` (Int): Returns the first n elements from the list.
  * `last` (Int): Returns the last n elements from the list.
  * `orderBy` (TeamRepositoryOrder): Order for the connection.
  * `query` (String): The search string to look for. Repositories will be returned where the name contains your search string.

* `repositoriesResourcePath` (URI!): The HTTP path for this team's repositories.
* `repositoriesUrl` (URI!): The HTTP URL for this team's repositories.
* `resourcePath` (URI!): The HTTP path for this team.
* `reviewRequestDelegationAlgorithm` (TeamReviewAssignmentAlgorithm): What algorithm is used for review assignment for this team.
* `reviewRequestDelegationEnabled` (Boolean!): True if review assignment is enabled for this team.
* `reviewRequestDelegationMemberCount` (Int): How many team members are required for review assignment for this team.
* `reviewRequestDelegationNotifyTeam` (Boolean!): When assigning team members via delegation, whether the entire team should be notified as well.
* `slug` (String!): The slug corresponding to the team.
* `teamsResourcePath` (URI!): The HTTP path for this team's teams.
* `teamsUrl` (URI!): The HTTP URL for this team's teams.
* `updatedAt` (DateTime!): Identifies the date and time when the object was last updated.
* `url` (URI!): The HTTP URL for this team.
* `viewerCanAdminister` (Boolean!): Team is adminable by the viewer.
* `viewerCanSubscribe` (Boolean!): Check if the viewer is able to change their subscription status for the subscribable entity. **Deprecated:** Team.viewerCanSubscribe will be removed. Team notifications subscriptions are being deprecated. Removal on 2026-07-01 UTC.
* `viewerSubscription` (SubscriptionState): Identifies if the viewer is watching, not watching, or ignoring the subscribable entity. **Deprecated:** Team.viewerSubscription will be removed. Team notifications subscriptions are being deprecated. Removal on 2026-07-01 UTC.

## TeamAddMemberAuditEntry - object

Audit log entry for a team.add_member event.

**Implements:** AuditEntry, Node, OrganizationAuditEntryData, TeamAuditEntryData

### Fields for `TeamAddMemberAuditEntry`

* `action` (String!): The action name. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actor` (AuditEntryActor): The user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorIp` (String): The IP address of the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLocation` (ActorLocation): A readable representation of the actor's location. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLogin` (String): The username of the user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorResourcePath` (URI): The HTTP path for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorUrl` (URI): The HTTP URL for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `createdAt` (PreciseDateTime!): The time the action was initiated. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `id` (ID!): The Node ID of the TeamAddMemberAuditEntry object.
* `isLdapMapped` (Boolean): Whether the team was mapped to an LDAP Group. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `operationType` (OperationType): The corresponding operation type for the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organization` (Organization): The Organization associated with the Audit Entry. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationName` (String): The name of the Organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationResourcePath` (URI): The HTTP path for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationUrl` (URI): The HTTP URL for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.
* `user` (User): The user affected by the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userLogin` (String): For actions involving two users, the actor is the initiator and the user is the affected user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userResourcePath` (URI): The HTTP path for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userUrl` (URI): The HTTP URL for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.

## TeamAddRepositoryAuditEntry - object

Audit log entry for a team.add_repository event.

**Implements:** AuditEntry, Node, OrganizationAuditEntryData, RepositoryAuditEntryData, TeamAuditEntryData

### Fields for `TeamAddRepositoryAuditEntry`

* `action` (String!): The action name. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actor` (AuditEntryActor): The user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorIp` (String): The IP address of the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLocation` (ActorLocation): A readable representation of the actor's location. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLogin` (String): The username of the user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorResourcePath` (URI): The HTTP path for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorUrl` (URI): The HTTP URL for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `createdAt` (PreciseDateTime!): The time the action was initiated. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `id` (ID!): The Node ID of the TeamAddRepositoryAuditEntry object.
* `isLdapMapped` (Boolean): Whether the team was mapped to an LDAP Group. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `operationType` (OperationType): The corresponding operation type for the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organization` (Organization): The Organization associated with the Audit Entry. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationName` (String): The name of the Organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationResourcePath` (URI): The HTTP path for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationUrl` (URI): The HTTP URL for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `repository` (Repository): The repository associated with the action.
* `repositoryName` (String): The name of the repository.
* `repositoryResourcePath` (URI): The HTTP path for the repository.
* `repositoryUrl` (URI): The HTTP URL for the repository.
* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.
* `user` (User): The user affected by the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userLogin` (String): For actions involving two users, the actor is the initiator and the user is the affected user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userResourcePath` (URI): The HTTP path for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userUrl` (URI): The HTTP URL for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.

## TeamAuditEntryData - interface

Metadata for an audit entry with action team.*.

### Fields for `TeamAuditEntryData`

* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.

### Implemented by

* OrgRestoreMemberMembershipTeamAuditEntryData
* TeamAddMemberAuditEntry
* TeamAddRepositoryAuditEntry
* TeamChangeParentTeamAuditEntry
* TeamRemoveMemberAuditEntry
* TeamRemoveRepositoryAuditEntry

## TeamChangeParentTeamAuditEntry - object

Audit log entry for a team.change_parent_team event.

**Implements:** AuditEntry, Node, OrganizationAuditEntryData, TeamAuditEntryData

### Fields for `TeamChangeParentTeamAuditEntry`

* `action` (String!): The action name. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actor` (AuditEntryActor): The user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorIp` (String): The IP address of the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLocation` (ActorLocation): A readable representation of the actor's location. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLogin` (String): The username of the user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorResourcePath` (URI): The HTTP path for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorUrl` (URI): The HTTP URL for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `createdAt` (PreciseDateTime!): The time the action was initiated. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `id` (ID!): The Node ID of the TeamChangeParentTeamAuditEntry object.
* `isLdapMapped` (Boolean): Whether the team was mapped to an LDAP Group. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `operationType` (OperationType): The corresponding operation type for the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organization` (Organization): The Organization associated with the Audit Entry. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationName` (String): The name of the Organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationResourcePath` (URI): The HTTP path for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationUrl` (URI): The HTTP URL for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeam` (Team): The new parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamName` (String): The name of the new parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamNameWas` (String): The name of the former parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamResourcePath` (URI): The HTTP path for the parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamUrl` (URI): The HTTP URL for the parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamWas` (Team): The former parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamWasResourcePath` (URI): The HTTP path for the previous parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `parentTeamWasUrl` (URI): The HTTP URL for the previous parent team. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.
* `user` (User): The user affected by the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userLogin` (String): For actions involving two users, the actor is the initiator and the user is the affected user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userResourcePath` (URI): The HTTP path for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userUrl` (URI): The HTTP URL for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.

## TeamConnection - object

The connection type for Team.

### Fields for `TeamConnection`

* `edges` ([TeamEdge]): A list of edges.
* `nodes` ([Team]): A list of nodes.
* `pageInfo` (PageInfo!): Information to aid in pagination.
* `totalCount` (Int!): Identifies the total count of items in the connection.

## TeamEdge - object

An edge in a connection.

### Fields for `TeamEdge`

* `cursor` (String!): A cursor for use in pagination.
* `node` (Team): The item at the end of the edge.

## TeamMemberOrder - input object

Ordering options for team member connections.

### Input fields for `TeamMemberOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (TeamMemberOrderField!): The field to order team members by.

## TeamMemberOrderField - enum

Properties by which team member connections can be ordered.

### Values for `TeamMemberOrderField`

* `CREATED_AT`: Order team members by creation time.
* `LOGIN`: Order team members by login.

## TeamMemberRole - enum

The possible team member roles; eithermaintaineror 'member'.

### Values for `TeamMemberRole`

* `MAINTAINER`: A team maintainer has permission to add and remove team members.
* `MEMBER`: A team member has no administrative permissions on the team.

## TeamMembershipType - enum

Defines which types of team members are included in the returned list. Can be one of IMMEDIATE, CHILD_TEAM or ALL.

### Values for `TeamMembershipType`

* `ALL`: Includes immediate and child team members for the team.
* `CHILD_TEAM`: Includes only child team members for the team.
* `IMMEDIATE`: Includes only immediate members of the team.

## TeamNotificationSetting - enum

The possible team notification values.

### Values for `TeamNotificationSetting`

* `NOTIFICATIONS_DISABLED`: No one will receive notifications.
* `NOTIFICATIONS_ENABLED`: Everyone will receive notifications when the team is @mentioned.

## TeamOrder - input object

Ways in which team connections can be ordered.

### Input fields for `TeamOrder`

* `direction` (OrderDirection!): The direction in which to order nodes.
* `field` (TeamOrderField!): The field in which to order nodes by.

## TeamOrderField - enum

Properties by which team connections can be ordered.

### Values for `TeamOrderField`

* `NAME`: Allows ordering a list of teams by name.

## TeamPrivacy - enum

The possible team privacy values.

### Values for `TeamPrivacy`

* `SECRET`: A secret team can only be seen by its members.
* `VISIBLE`: A visible team can be seen and @mentioned by every member of the organization.

## TeamRemoveMemberAuditEntry - object

Audit log entry for a team.remove_member event.

**Implements:** AuditEntry, Node, OrganizationAuditEntryData, TeamAuditEntryData

### Fields for `TeamRemoveMemberAuditEntry`

* `action` (String!): The action name. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actor` (AuditEntryActor): The user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorIp` (String): The IP address of the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLocation` (ActorLocation): A readable representation of the actor's location. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLogin` (String): The username of the user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorResourcePath` (URI): The HTTP path for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorUrl` (URI): The HTTP URL for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `createdAt` (PreciseDateTime!): The time the action was initiated. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `id` (ID!): The Node ID of the TeamRemoveMemberAuditEntry object.
* `isLdapMapped` (Boolean): Whether the team was mapped to an LDAP Group. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `operationType` (OperationType): The corresponding operation type for the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organization` (Organization): The Organization associated with the Audit Entry. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationName` (String): The name of the Organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationResourcePath` (URI): The HTTP path for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationUrl` (URI): The HTTP URL for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.
* `user` (User): The user affected by the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userLogin` (String): For actions involving two users, the actor is the initiator and the user is the affected user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userResourcePath` (URI): The HTTP path for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userUrl` (URI): The HTTP URL for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.

## TeamRemoveRepositoryAuditEntry - object

Audit log entry for a team.remove_repository event.

**Implements:** AuditEntry, Node, OrganizationAuditEntryData, RepositoryAuditEntryData, TeamAuditEntryData

### Fields for `TeamRemoveRepositoryAuditEntry`

* `action` (String!): The action name. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actor` (AuditEntryActor): The user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorIp` (String): The IP address of the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLocation` (ActorLocation): A readable representation of the actor's location. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorLogin` (String): The username of the user who initiated the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorResourcePath` (URI): The HTTP path for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `actorUrl` (URI): The HTTP URL for the actor. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `createdAt` (PreciseDateTime!): The time the action was initiated. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `id` (ID!): The Node ID of the TeamRemoveRepositoryAuditEntry object.
* `isLdapMapped` (Boolean): Whether the team was mapped to an LDAP Group. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `operationType` (OperationType): The corresponding operation type for the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organization` (Organization): The Organization associated with the Audit Entry. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationName` (String): The name of the Organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationResourcePath` (URI): The HTTP path for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `organizationUrl` (URI): The HTTP URL for the organization. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `repository` (Repository): The repository associated with the action.
* `repositoryName` (String): The name of the repository.
* `repositoryResourcePath` (URI): The HTTP path for the repository.
* `repositoryUrl` (URI): The HTTP URL for the repository.
* `team` (Team): The team associated with the action.
* `teamName` (String): The name of the team.
* `teamResourcePath` (URI): The HTTP path for this team.
* `teamUrl` (URI): The HTTP URL for this team.
* `user` (User): The user affected by the action. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userLogin` (String): For actions involving two users, the actor is the initiator and the user is the affected user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userResourcePath` (URI): The HTTP path for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.
* `userUrl` (URI): The HTTP URL for the user. **Deprecated:** The GraphQL audit-log is deprecated. Please use the REST API instead. Removal on 2026-04-01 UTC.

## TeamRepositoryOrder - input object

Ordering options for team repository connections.

### Input fields for `TeamRepositoryOrder`

* `direction` (OrderDirection!): The ordering direction.
* `field` (TeamRepositoryOrderField!): The field to order repositories by.

## TeamRepositoryOrderField - enum

Properties by which team repository connections can be ordered.

### Values for `TeamRepositoryOrderField`

* `CREATED_AT`: Order repositories by creation time.
* `NAME`: Order repositories by name.
* `PERMISSION`: Order repositories by permission.
* `PUSHED_AT`: Order repositories by push time.
* `STARGAZERS`: Order repositories by number of stargazers.
* `UPDATED_AT`: Order repositories by update time.

## TeamReviewAssignmentAlgorithm - enum

The possible team review assignment algorithms.

### Values for `TeamReviewAssignmentAlgorithm`

* `LOAD_BALANCE`: Balance review load across the entire team.
* `ROUND_ROBIN`: Alternate reviews between each team member.

## TeamReviewRequestable - interface

Represents a team that can be requested to review a pull request.

### Fields for `TeamReviewRequestable`

* `id` (ID!): The Node ID of the TeamReviewRequestable object.
* `name` (String!): The name of the team.
* `slug` (String!): A unique, human-readable identifier for the team.

### Implemented by

* EnterpriseTeam
* Team

## TeamRole - enum

The role of a user on a team.

### Values for `TeamRole`

* `ADMIN`: User has admin rights on the team.
* `MEMBER`: User is a member of the team.

## updateTeamsRepository - mutation

Update team repository.

### Input fields for `updateTeamsRepository`

* `input` (UpdateTeamsRepositoryInput!): 

### Return fields for `updateTeamsRepository`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `repository` (Repository): The repository that was updated.
* `teams` ([Team!]): The teams granted permission on the repository.

## UpdateTeamsRepositoryInput - input object

Autogenerated input type of UpdateTeamsRepository.

### Input fields for `UpdateTeamsRepositoryInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `permission` (RepositoryPermission!): Permission that should be granted to the teams.
* `repositoryId` (ID!): Repository ID being granted access to.
* `teamIds` ([ID!]!): A list of teams being granted access. Limit: 10.