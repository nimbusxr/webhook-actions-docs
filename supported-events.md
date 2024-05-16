# Supported Events
- branch_protection_rule
- branch_protection_rule_created
- branch_protection_rule_deleted
- branch_protection_rule_edited
- check_run
- check_run_completed
- check_run_created
- check_run_requested_action
- check_run_rerequested
- check_suite
- check_suite_completed
- check_suite_requested
- check_suite_rerequested
- code_scanning_alert
- code_scanning_alert_appeared_in_branch
- code_scanning_alert_closed_by_user
- code_scanning_alert_created
- code_scanning_alert_fixed
- code_scanning_alert_reopened
- code_scanning_alert_reopened_by_user
- commit_comment
- commit_comment_created
- create
- delete
- dependabot_alert
- dependabot_alert_created
- dependabot_alert_dismissed
- dependabot_alert_fixed
- dependabot_alert_reintroduced
- dependabot_alert_reopened
- deploy_key
- deploy_key_created
- deploy_key_deleted
- deployment
- deployment_created
- deployment_status
- deployment_status_created
- discussion
- discussion_answered
- discussion_category_changed
- discussion_created
- discussion_deleted
- discussion_edited
- discussion_labeled
- discussion_locked
- discussion_pinned
- discussion_transferred
- discussion_unanswered
- discussion_unlabeled
- discussion_unlocked
- discussion_unpinned
- discussion_comment
- discussion_comment_created
- discussion_comment_deleted
- discussion_comment_edited
- fork
- github_app_authorization
- github_app_authorization_revoked
- gollum
- installation
- installation_created
- installation_deleted
- installation_new_permissions_accepted
- installation_suspend
- installation_unsuspend
- installation_repositories
- installation_repositories_added
- installation_repositories_removed
- issue_comment
- issue_comment_created
- issue_comment_deleted
- issue_comment_edited
- issues
- issues_assigned
- issues_closed
- issues_deleted
- issues_demilestoned
- issues_edited
- issues_labeled
- issues_locked
- issues_milestoned
- issues_opened
- issues_pinned
- issues_reopened
- issues_transferred
- issues_unassigned
- issues_unlabeled
- issues_unlocked
- issues_unpinned
- label
- label_created
- label_deleted
- label_edited
- marketplace_purchase
- marketplace_purchase_cancelled
- marketplace_purchase_changed
- marketplace_purchase_pending_change
- marketplace_purchase_pending_change_cancelled
- marketplace_purchase_purchased
- member
- member_added
- member_edited
- member_removed
- membership
- membership_added
- membership_removed
- merge_group
- merge_group_checks_requested
- meta
- meta_deleted
- milestone
- milestone_closed
- milestone_created
- milestone_deleted
- milestone_edited
- milestone_opened
- org_block
- org_block_blocked
- org_block_unblocked
- organization
- organization_deleted
- organization_member_added
- organization_member_invited
- organization_member_removed
- organization_renamed
- package
- package_published
- package_updated
- page_build
- ping
- project
- project_closed
- project_created
- project_deleted
- project_edited
- project_reopened
- project_card
- project_card_converted
- project_card_created
- project_card_deleted
- project_card_edited
- project_card_moved
- project_column
- project_column_created
- project_column_deleted
- project_column_edited
- project_column_moved
- projects_v2_item
- projects_v2_item_archived
- projects_v2_item_converted
- projects_v2_item_created
- projects_v2_item_deleted
- projects_v2_item_edited
- projects_v2_item_reordered
- projects_v2_item_restored
- public
- pull_request
- pull_request_assigned
- pull_request_auto_merge_disabled
- pull_request_auto_merge_enabled
- pull_request_closed
- pull_request_converted_to_draft
- pull_request_dequeued
- pull_request_edited
- pull_request_labeled
- pull_request_locked
- pull_request_opened
- pull_request_queued
- pull_request_ready_for_review
- pull_request_reopened
- pull_request_review_request_removed
- pull_request_review_requested
- pull_request_synchronize
- pull_request_unassigned
- pull_request_unlabeled
- pull_request_unlocked
- pull_request_review
- pull_request_review_dismissed
- pull_request_review_edited
- pull_request_review_submitted
- pull_request_review_comment
- pull_request_review_comment_created
- pull_request_review_comment_deleted
- pull_request_review_comment_edited
- pull_request_review_thread
- pull_request_review_thread_resolved
- pull_request_review_thread_unresolved
- push
- release
- release_created
- release_deleted
- release_edited
- release_prereleased
- release_published
- release_released
- release_unpublished
- repository
- repository_archived
- repository_created
- repository_deleted
- repository_edited
- repository_privatized
- repository_publicized
- repository_renamed
- repository_transferred
- repository_unarchived
- repository_dispatch
  - See [how to dispatch between repositories](./examples/remote-repository-dispatch.md)
- repository_import
- repository_vulnerability_alert
- repository_vulnerability_alert_create
- repository_vulnerability_alert_dismiss
- repository_vulnerability_alert_reopen
- repository_vulnerability_alert_resolve
- secret_scanning_alert
- secret_scanning_alert_created
- secret_scanning_alert_reopened
- secret_scanning_alert_resolved
- security_advisory
- security_advisory_performed
- security_advisory_published
- security_advisory_updated
- security_advisory_withdrawn
- sponsorship
- sponsorship_cancelled
- sponsorship_created
- sponsorship_edited
- sponsorship_pending_cancellation
- sponsorship_pending_tier_change
- sponsorship_tier_changed
- star
- star_created
- star_deleted
- status
- team
- team_added_to_repository
- team_created
- team_deleted
- team_edited
- team_removed_from_repository
- team_add
- watch
- watch_started
- workflow_dispatch
- workflow_job
- workflow_job_completed
- workflow_job_in_progress
- workflow_job_queued
- workflow_run
- workflow_run_completed
- workflow_run_in_progress
- workflow_run_requested

Please see [GitHub Webhooks Documentation](https://docs.github.com/en/developers/webhooks-and-events/webhooks/webhook-events-and-payloads) and
[GitHub Repository Dispatch Documentation](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#repository_dispatch) for further information.