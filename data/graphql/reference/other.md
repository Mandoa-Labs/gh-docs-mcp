# Other

Reference documentation for GraphQL schema types in the Other category.

## Base64String - scalar

A (potentially binary) string encoded using base64.

## BigInt - scalar

Represents non-fractional signed whole numeric values. Since the value may
exceed the size of a 32-bit integer, it's encoded as a string.

## Boolean - scalar

Represents true or false values.

## CustomPropertyValue - scalar

A custom property value can be either a string or an array of strings. All
property types support only a single string value, except for the multi-select
type, which supports only a string array.

## Date - scalar

An ISO-8601 encoded date string.

## DateTime - scalar

An ISO-8601 encoded UTC date string.

## Float - scalar

Represents signed double-precision fractional values as specified by IEEE 754.

## GitObjectID - scalar

A Git object ID.

## GitRefname - scalar

A fully qualified reference name (e.g. refs/heads/master).

## GitSSHRemote - scalar

Git SSH string.

## GitTimestamp - scalar

An ISO-8601 encoded date string. Unlike the DateTime type, GitTimestamp is not converted in UTC.

## HTML - scalar

A string containing HTML code.

## id - query

ID of the object.

**Type:** ID!

## ID - scalar

Represents a unique identifier that is Base64 obfuscated. It is often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as "VXNlci0xMA==") or integer (such as 4) input value will be accepted as an ID.

## Int - scalar

Represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

## IssueTimelineItemsItemType - enum

The possible item types found in a timeline.

### Values for `IssueTimelineItemsItemType`

* `ADDED_TO_PROJECT_EVENT`: Represents aadded_to_projectevent on a given issue or pull request.
* `ADDED_TO_PROJECT_V2_EVENT`: Represents aadded_to_project_v2event on a given issue or pull request.
* `ASSIGNED_EVENT`: Represents anassignedevent on any assignable object.
* `BLOCKED_BY_ADDED_EVENT`: Represents ablocked_by_addedevent on a given issue.
* `BLOCKED_BY_REMOVED_EVENT`: Represents ablocked_by_removedevent on a given issue.
* `BLOCKING_ADDED_EVENT`: Represents ablocking_addedevent on a given issue.
* `BLOCKING_REMOVED_EVENT`: Represents ablocking_removedevent on a given issue.
* `CLOSED_EVENT`: Represents aclosedevent on any Closable.
* `COMMENT_DELETED_EVENT`: Represents acomment_deletedevent on a given issue or pull request.
* `CONNECTED_EVENT`: Represents aconnectedevent on a given issue or pull request.
* `CONVERTED_FROM_DRAFT_EVENT`: Represents aconverted_from_draftevent on a given issue or pull request.
* `CONVERTED_NOTE_TO_ISSUE_EVENT`: Represents aconverted_note_to_issueevent on a given issue or pull request.
* `CONVERTED_TO_DISCUSSION_EVENT`: Represents aconverted_to_discussionevent on a given issue.
* `CROSS_REFERENCED_EVENT`: Represents a mention made by one issue or pull request to another.
* `DEMILESTONED_EVENT`: Represents ademilestonedevent on a given issue or pull request.
* `DISCONNECTED_EVENT`: Represents adisconnectedevent on a given issue or pull request.
* `ISSUE_COMMENT`: Represents a comment on an Issue.
* `ISSUE_COMMENT_PINNED_EVENT`: Represents aissue_comment_pinnedevent on a given issue.
* `ISSUE_COMMENT_UNPINNED_EVENT`: Represents aissue_comment_unpinnedevent on a given issue.
* `ISSUE_FIELD_ADDED_EVENT`: Represents aissue_field_addedevent on a given issue.
* `ISSUE_FIELD_CHANGED_EVENT`: Represents aissue_field_changedevent on a given issue.
* `ISSUE_FIELD_REMOVED_EVENT`: Represents aissue_field_removedevent on a given issue.
* `ISSUE_TYPE_ADDED_EVENT`: Represents aissue_type_addedevent on a given issue.
* `ISSUE_TYPE_CHANGED_EVENT`: Represents aissue_type_changedevent on a given issue.
* `ISSUE_TYPE_REMOVED_EVENT`: Represents aissue_type_removedevent on a given issue.
* `LABELED_EVENT`: Represents alabeledevent on a given issue or pull request.
* `LOCKED_EVENT`: Represents alockedevent on a given issue or pull request.
* `MARKED_AS_DUPLICATE_EVENT`: Represents amarked_as_duplicateevent on a given issue or pull request.
* `MENTIONED_EVENT`: Represents amentionedevent on a given issue or pull request.
* `MILESTONED_EVENT`: Represents amilestonedevent on a given issue or pull request.
* `MOVED_COLUMNS_IN_PROJECT_EVENT`: Represents amoved_columns_in_projectevent on a given issue or pull request.
* `PARENT_ISSUE_ADDED_EVENT`: Represents aparent_issue_addedevent on a given issue.
* `PARENT_ISSUE_REMOVED_EVENT`: Represents aparent_issue_removedevent on a given issue.
* `PINNED_EVENT`: Represents apinnedevent on a given issue or pull request.
* `PROJECT_V2_ITEM_STATUS_CHANGED_EVENT`: Represents aproject_v2_item_status_changedevent on a given issue or pull request.
* `REFERENCED_EVENT`: Represents areferencedevent on a given ReferencedSubject.
* `REMOVED_FROM_PROJECT_EVENT`: Represents aremoved_from_projectevent on a given issue or pull request.
* `REMOVED_FROM_PROJECT_V2_EVENT`: Represents aremoved_from_project_v2event on a given issue or pull request.
* `RENAMED_TITLE_EVENT`: Represents arenamedevent on a given issue or pull request.
* `REOPENED_EVENT`: Represents areopenedevent on any Closable.
* `SUBSCRIBED_EVENT`: Represents asubscribedevent on a given Subscribable.
* `SUB_ISSUE_ADDED_EVENT`: Represents asub_issue_addedevent on a given issue.
* `SUB_ISSUE_REMOVED_EVENT`: Represents asub_issue_removedevent on a given issue.
* `TRANSFERRED_EVENT`: Represents atransferredevent on a given issue or pull request.
* `UNASSIGNED_EVENT`: Represents anunassignedevent on any assignable object.
* `UNLABELED_EVENT`: Represents anunlabeledevent on a given issue or pull request.
* `UNLOCKED_EVENT`: Represents anunlockedevent on a given issue or pull request.
* `UNMARKED_AS_DUPLICATE_EVENT`: Represents anunmarked_as_duplicateevent on a given issue or pull request.
* `UNPINNED_EVENT`: Represents anunpinnedevent on a given issue or pull request.
* `UNSUBSCRIBED_EVENT`: Represents anunsubscribedevent on a given Subscribable.
* `USER_BLOCKED_EVENT`: Represents auser_blockedevent on a given user.

## PageInfo - object

Information about pagination in a connection.

### Fields for `PageInfo`

* `endCursor` (String): When paginating forwards, the cursor to continue.
* `hasNextPage` (Boolean!): When paginating forwards, are there more items?.
* `hasPreviousPage` (Boolean!): When paginating backwards, are there more items?.
* `startCursor` (String): When paginating backwards, the cursor to continue.

## PreciseDateTime - scalar

An ISO-8601 encoded UTC date string with millisecond precision.

## PullRequestTimelineItemsItemType - enum

The possible item types found in a timeline.

### Values for `PullRequestTimelineItemsItemType`

* `ADDED_TO_MERGE_QUEUE_EVENT`: Represents anadded_to_merge_queueevent on a given pull request.
* `ADDED_TO_PROJECT_EVENT`: Represents aadded_to_projectevent on a given issue or pull request.
* `ADDED_TO_PROJECT_V2_EVENT`: Represents aadded_to_project_v2event on a given issue or pull request.
* `ASSIGNED_EVENT`: Represents anassignedevent on any assignable object.
* `AUTOMATIC_BASE_CHANGE_FAILED_EVENT`: Represents aautomatic_base_change_failedevent on a given pull request.
* `AUTOMATIC_BASE_CHANGE_SUCCEEDED_EVENT`: Represents aautomatic_base_change_succeededevent on a given pull request.
* `AUTO_MERGE_DISABLED_EVENT`: Represents aauto_merge_disabledevent on a given pull request.
* `AUTO_MERGE_ENABLED_EVENT`: Represents aauto_merge_enabledevent on a given pull request.
* `AUTO_REBASE_ENABLED_EVENT`: Represents aauto_rebase_enabledevent on a given pull request.
* `AUTO_SQUASH_ENABLED_EVENT`: Represents aauto_squash_enabledevent on a given pull request.
* `BASE_REF_CHANGED_EVENT`: Represents abase_ref_changedevent on a given issue or pull request.
* `BASE_REF_DELETED_EVENT`: Represents abase_ref_deletedevent on a given pull request.
* `BASE_REF_FORCE_PUSHED_EVENT`: Represents abase_ref_force_pushedevent on a given pull request.
* `BLOCKED_BY_ADDED_EVENT`: Represents ablocked_by_addedevent on a given issue.
* `BLOCKED_BY_REMOVED_EVENT`: Represents ablocked_by_removedevent on a given issue.
* `BLOCKING_ADDED_EVENT`: Represents ablocking_addedevent on a given issue.
* `BLOCKING_REMOVED_EVENT`: Represents ablocking_removedevent on a given issue.
* `CLOSED_EVENT`: Represents aclosedevent on any Closable.
* `COMMENT_DELETED_EVENT`: Represents acomment_deletedevent on a given issue or pull request.
* `CONNECTED_EVENT`: Represents aconnectedevent on a given issue or pull request.
* `CONVERTED_FROM_DRAFT_EVENT`: Represents aconverted_from_draftevent on a given issue or pull request.
* `CONVERTED_NOTE_TO_ISSUE_EVENT`: Represents aconverted_note_to_issueevent on a given issue or pull request.
* `CONVERTED_TO_DISCUSSION_EVENT`: Represents aconverted_to_discussionevent on a given issue.
* `CONVERT_TO_DRAFT_EVENT`: Represents aconvert_to_draftevent on a given pull request.
* `CROSS_REFERENCED_EVENT`: Represents a mention made by one issue or pull request to another.
* `DEMILESTONED_EVENT`: Represents ademilestonedevent on a given issue or pull request.
* `DEPLOYED_EVENT`: Represents adeployedevent on a given pull request.
* `DEPLOYMENT_ENVIRONMENT_CHANGED_EVENT`: Represents adeployment_environment_changedevent on a given pull request.
* `DISCONNECTED_EVENT`: Represents adisconnectedevent on a given issue or pull request.
* `HEAD_REF_DELETED_EVENT`: Represents ahead_ref_deletedevent on a given pull request.
* `HEAD_REF_FORCE_PUSHED_EVENT`: Represents ahead_ref_force_pushedevent on a given pull request.
* `HEAD_REF_RESTORED_EVENT`: Represents ahead_ref_restoredevent on a given pull request.
* `ISSUE_COMMENT`: Represents a comment on an Issue.
* `ISSUE_COMMENT_PINNED_EVENT`: Represents aissue_comment_pinnedevent on a given issue.
* `ISSUE_COMMENT_UNPINNED_EVENT`: Represents aissue_comment_unpinnedevent on a given issue.
* `ISSUE_FIELD_ADDED_EVENT`: Represents aissue_field_addedevent on a given issue.
* `ISSUE_FIELD_CHANGED_EVENT`: Represents aissue_field_changedevent on a given issue.
* `ISSUE_FIELD_REMOVED_EVENT`: Represents aissue_field_removedevent on a given issue.
* `ISSUE_TYPE_ADDED_EVENT`: Represents aissue_type_addedevent on a given issue.
* `ISSUE_TYPE_CHANGED_EVENT`: Represents aissue_type_changedevent on a given issue.
* `ISSUE_TYPE_REMOVED_EVENT`: Represents aissue_type_removedevent on a given issue.
* `LABELED_EVENT`: Represents alabeledevent on a given issue or pull request.
* `LOCKED_EVENT`: Represents alockedevent on a given issue or pull request.
* `MARKED_AS_DUPLICATE_EVENT`: Represents amarked_as_duplicateevent on a given issue or pull request.
* `MENTIONED_EVENT`: Represents amentionedevent on a given issue or pull request.
* `MERGED_EVENT`: Represents amergedevent on a given pull request.
* `MILESTONED_EVENT`: Represents amilestonedevent on a given issue or pull request.
* `MOVED_COLUMNS_IN_PROJECT_EVENT`: Represents amoved_columns_in_projectevent on a given issue or pull request.
* `PARENT_ISSUE_ADDED_EVENT`: Represents aparent_issue_addedevent on a given issue.
* `PARENT_ISSUE_REMOVED_EVENT`: Represents aparent_issue_removedevent on a given issue.
* `PINNED_EVENT`: Represents apinnedevent on a given issue or pull request.
* `PROJECT_V2_ITEM_STATUS_CHANGED_EVENT`: Represents aproject_v2_item_status_changedevent on a given issue or pull request.
* `PULL_REQUEST_COMMIT`: Represents a Git commit part of a pull request.
* `PULL_REQUEST_COMMIT_COMMENT_THREAD`: Represents a commit comment thread part of a pull request.
* `PULL_REQUEST_REVIEW`: A review object for a given pull request.
* `PULL_REQUEST_REVIEW_THREAD`: A threaded list of comments for a given pull request.
* `PULL_REQUEST_REVISION_MARKER`: Represents the latest point in the pull request timeline for which the viewer has seen the pull request's commits.
* `READY_FOR_REVIEW_EVENT`: Represents aready_for_reviewevent on a given pull request.
* `REFERENCED_EVENT`: Represents areferencedevent on a given ReferencedSubject.
* `REMOVED_FROM_MERGE_QUEUE_EVENT`: Represents aremoved_from_merge_queueevent on a given pull request.
* `REMOVED_FROM_PROJECT_EVENT`: Represents aremoved_from_projectevent on a given issue or pull request.
* `REMOVED_FROM_PROJECT_V2_EVENT`: Represents aremoved_from_project_v2event on a given issue or pull request.
* `RENAMED_TITLE_EVENT`: Represents arenamedevent on a given issue or pull request.
* `REOPENED_EVENT`: Represents areopenedevent on any Closable.
* `REVIEW_DISMISSED_EVENT`: Represents areview_dismissedevent on a given issue or pull request.
* `REVIEW_REQUESTED_EVENT`: Represents anreview_requestedevent on a given pull request.
* `REVIEW_REQUEST_REMOVED_EVENT`: Represents anreview_request_removedevent on a given pull request.
* `SUBSCRIBED_EVENT`: Represents asubscribedevent on a given Subscribable.
* `SUB_ISSUE_ADDED_EVENT`: Represents asub_issue_addedevent on a given issue.
* `SUB_ISSUE_REMOVED_EVENT`: Represents asub_issue_removedevent on a given issue.
* `TRANSFERRED_EVENT`: Represents atransferredevent on a given issue or pull request.
* `UNASSIGNED_EVENT`: Represents anunassignedevent on any assignable object.
* `UNLABELED_EVENT`: Represents anunlabeledevent on a given issue or pull request.
* `UNLOCKED_EVENT`: Represents anunlockedevent on a given issue or pull request.
* `UNMARKED_AS_DUPLICATE_EVENT`: Represents anunmarked_as_duplicateevent on a given issue or pull request.
* `UNPINNED_EVENT`: Represents anunpinnedevent on a given issue or pull request.
* `UNSUBSCRIBED_EVENT`: Represents anunsubscribedevent on a given Subscribable.
* `USER_BLOCKED_EVENT`: Represents auser_blockedevent on a given user.

## relay - query

Workaround for re-exposing the root query object. (Refer to
https://github.com/facebook/relay/issues/112 for more information.).

**Type:** Query!

## RepositoryRuleType - enum

The rule types supported in rulesets.

### Values for `RepositoryRuleType`

* `AUTHORIZATION`: Authorization.
* `BRANCH_NAME_PATTERN`: Branch name pattern.
* `CODE_SCANNING`: Choose which tools must provide code scanning results before the reference is
updated. When configured, code scanning must be enabled and have results for
both the commit and the reference being updated.
* `COMMITTER_EMAIL_PATTERN`: Committer email pattern.
* `COMMIT_AUTHOR_EMAIL_PATTERN`: Commit author email pattern.
* `COMMIT_MESSAGE_PATTERN`: Commit message pattern.
* `COPILOT_CODE_REVIEW`: Request Copilot code review for new pull requests automatically if the author
has access to Copilot code review and their premium requests quota has not
reached the limit.
* `CREATION`: Only allow users with bypass permission to create matching refs.
* `DELETION`: Only allow users with bypass permissions to delete matching refs.
* `FILE_EXTENSION_RESTRICTION`: Prevent commits that include files with specified file extensions from being pushed to the commit graph.
* `FILE_PATH_RESTRICTION`: Prevent commits that include changes in specified file and folder paths from
being pushed to the commit graph. This includes absolute paths that contain file names.
* `LOCK_BRANCH`: Branch is read-only. Users cannot push to the branch.
* `MAX_FILE_PATH_LENGTH`: Prevent commits that include file paths that exceed the specified character limit from being pushed to the commit graph.
* `MAX_FILE_SIZE`: Prevent commits with individual files that exceed the specified limit from being pushed to the commit graph.
* `MAX_REF_UPDATES`: Max ref updates.
* `MERGE_QUEUE`: Merges must be performed via a merge queue.
* `MERGE_QUEUE_LOCKED_REF`: Merge queue locked ref.
* `NON_FAST_FORWARD`: Prevent users with push access from force pushing to refs.
* `PULL_REQUEST`: Require all commits be made to a non-target branch and submitted via a pull request before they can be merged.
* `REQUIRED_DEPLOYMENTS`: Choose which environments must be successfully deployed to before refs can be pushed into a ref that matches this rule.
* `REQUIRED_LINEAR_HISTORY`: Prevent merge commits from being pushed to matching refs.
* `REQUIRED_REVIEW_THREAD_RESOLUTION`: When enabled, all conversations on code must be resolved before a pull request
can be merged into a branch that matches this rule.
* `REQUIRED_SIGNATURES`: Commits pushed to matching refs must have verified signatures.
* `REQUIRED_STATUS_CHECKS`: Choose which status checks must pass before the ref is updated. When enabled,
commits must first be pushed to another ref where the checks pass.
* `REQUIRED_WORKFLOW_STATUS_CHECKS`: Require all commits be made to a non-target branch and submitted via a pull
request and required workflow checks to pass before they can be merged.
* `SECRET_SCANNING`: Secret scanning.
* `TAG`: Tag.
* `TAG_NAME_PATTERN`: Tag name pattern.
* `UPDATE`: Only allow users with bypass permission to update matching refs.
* `WORKFLOWS`: Require all changes made to a targeted branch to pass the specified workflows before they can be merged.
* `WORKFLOW_UPDATES`: Workflow files cannot be modified.

## RuleParameters - union

Types which can be parameters for RepositoryRule objects.

### Possible types for `RuleParameters`

* BranchNamePatternParameters
* CodeScanningParameters
* CommitAuthorEmailPatternParameters
* CommitMessagePatternParameters
* CommitterEmailPatternParameters
* CopilotCodeReviewParameters
* FileExtensionRestrictionParameters
* FilePathRestrictionParameters
* MaxFilePathLengthParameters
* MaxFileSizeParameters
* MergeQueueParameters
* PullRequestParameters
* RequiredDeploymentsParameters
* RequiredStatusChecksParameters
* TagNamePatternParameters
* UpdateParameters
* WorkflowsParameters

## RuleParametersInput - input object

Specifies the parameters for a RepositoryRule object. Only one of the fields should be specified.

### Input fields for `RuleParametersInput`

* `branchNamePattern` (BranchNamePatternParametersInput): Parameters used for the branch_name_pattern rule type.
* `codeScanning` (CodeScanningParametersInput): Parameters used for the code_scanning rule type.
* `commitAuthorEmailPattern` (CommitAuthorEmailPatternParametersInput): Parameters used for the commit_author_email_pattern rule type.
* `commitMessagePattern` (CommitMessagePatternParametersInput): Parameters used for the commit_message_pattern rule type.
* `committerEmailPattern` (CommitterEmailPatternParametersInput): Parameters used for the committer_email_pattern rule type.
* `copilotCodeReview` (CopilotCodeReviewParametersInput): Parameters used for the copilot_code_review rule type.
* `fileExtensionRestriction` (FileExtensionRestrictionParametersInput): Parameters used for the file_extension_restriction rule type.
* `filePathRestriction` (FilePathRestrictionParametersInput): Parameters used for the file_path_restriction rule type.
* `maxFilePathLength` (MaxFilePathLengthParametersInput): Parameters used for the max_file_path_length rule type.
* `maxFileSize` (MaxFileSizeParametersInput): Parameters used for the max_file_size rule type.
* `mergeQueue` (MergeQueueParametersInput): Parameters used for the merge_queue rule type.
* `pullRequest` (PullRequestParametersInput): Parameters used for the pull_request rule type.
* `requiredDeployments` (RequiredDeploymentsParametersInput): Parameters used for the required_deployments rule type.
* `requiredStatusChecks` (RequiredStatusChecksParametersInput): Parameters used for the required_status_checks rule type.
* `tagNamePattern` (TagNamePatternParametersInput): Parameters used for the tag_name_pattern rule type.
* `update` (UpdateParametersInput): Parameters used for the update rule type.
* `workflows` (WorkflowsParametersInput): Parameters used for the workflows rule type.

## String - scalar

Represents textual data as UTF-8 character sequences. This type is most often used by GraphQL to represent free-form human-readable text.

## URI - scalar

An RFC 3986, RFC 3987, and RFC 6570 (level 4) compliant URI string.

## X509Certificate - scalar

A valid x509 certificate string.