# Cortex Cloud APIs Postman Collection - Variable Guide

This document provides an overview of the Postman environment variables used in the "Cortex Cloud APIs" collection. Utilizing these variables allows for more flexible and reusable API requests.

## General Usage

Variables are defined at the collection level and can be referenced in request URLs, headers, and bodies using the `{{variable_name}}` syntax. This collection has been updated to use variables extensively in request bodies to make them more dynamic and easier to manage.

## Authentication Variables

These variables are standard for authenticating with the Cortex APIs and are typically used in the request headers.

*   `{{api-endpoint}}`:
    *   **Description**: The FQDN of your Cortex API endpoint.
    *   **Used In**: URL of all requests.
*   `{{X_API_KEY}}`:
    *   **Description**: Your Cortex API Key value.
    *   **Used In**: `Authorization` header of all requests.
*   `{{X_XDR_AUTH_ID}}`:
    *   **Description**: Your Cortex API Key ID.
    *   **Used In**: `x-xdr-auth-id` header of all requests.
*   `{{XSIAM_API_KEY}}`:
    *   **Description**: Your XSIAM API Key or Authorization header value (used for XSIAM specific APIs).
    *   **Used In**: Potentially in headers for XSIAM-specific APIs (not explicitly shown in body usage).

## Request Body Variables

The following variables are used within the JSON request bodies of various API calls.

### Common Variables

*   `{{instance_id}}`:
    *   **Description**: The specific instance ID to target for many operations.
    *   **Value Example**: `"YOUR_INSTANCE_ID"`
    *   **Used In APIs**:
        *   Enable or disable cloud accounts
        *   Get accounts in the specified integration instances
        *   Edit the specified integration instance template
        *   Get integration instance details
*   `{{cloud_provider}}`:
    *   **Description**: Cloud Service Provider (e.g., AWS, AZURE, GCP).
    *   **Value Example**: `"AWS"`
    *   **Used In APIs**:
        *   Get available regions for a CSP
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
        *   Create an outpost template
*   `{{custom_resources_tags_array}}`:
    *   **Description**: JSON array of key-value pairs for custom resource tags.
    *   **Value Example**: `"[{\"key\": \"environment\", \"value\": \"production\"}]"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
        *   Create an outpost template

### Cloud Accounts APIs

*   `{{cloud_account_ids_array}}`:
    *   **Description**: JSON array of cloud account IDs (e.g., for enabling/disabling).
    *   **Value Example**: `["account-1", "account-2"]`
    *   **Used In APIs**:
        *   Enable or disable cloud accounts
*   `{{enable_accounts_flag}}`:
    *   **Description**: Flag to enable (true) or disable (false) cloud accounts.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Enable or disable cloud accounts
*   `{{get_accounts_sort_field}}`:
    *   **Description**: Field to sort by when getting accounts (e.g., STATUS, NAME).
    *   **Value Example**: `"STATUS"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_sort_order}}`:
    *   **Description**: Sort order (ASC or DESC) when getting accounts.
    *   **Value Example**: `"DESC"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_paging_from}}`:
    *   **Description**: Starting index for pagination when getting accounts.
    *   **Value Example**: `"0"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_paging_to}}`:
    *   **Description**: Ending index for pagination when getting accounts.
    *   **Value Example**: `"50"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_filter_field}}`:
    *   **Description**: Field to filter on when getting accounts (e.g., STATUS).
    *   **Value Example**: `"STATUS"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_filter_type}}`:
    *   **Description**: Filter type (e.g., EQ, NEQ) when getting accounts.
    *   **Value Example**: `"EQ"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances
*   `{{get_accounts_filter_value}}`:
    *   **Description**: Value to filter by when getting accounts.
    *   **Value Example**: `"ACTIVE"`
    *   **Used In APIs**:
        *   Get accounts in the specified integration instances

### Cloud Integration Instances APIs

*   `{{scope_type}}`:
    *   **Description**: Scope for instance creation (e.g., ORGANIZATION, ACCOUNT).
    *   **Value Example**: `"ORGANIZATION"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
*   `{{scan_mode_type}}`:
    *   **Description**: Scan mode for instance creation (e.g., MANAGED, SELF_HOSTED).
    *   **Value Example**: `"MANAGED"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
*   `{{new_instance_name}}`:
    *   **Description**: Name for the new cloud onboarding instance.
    *   **Value Example**: `"My New Instance"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
*   `{{audit_logs_enabled}}`:
    *   **Description**: Flag to enable audit log collection.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{accounts_scope_enabled}}`:
    *   **Description**: Flag to enable account scope modifications.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{accounts_scope_type}}`:
    *   **Description**: Type of account scope modification (INCLUDE or EXCLUDE).
    *   **Value Example**: `"INCLUDE"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{scope_account_ids_array}}`:
    *   **Description**: JSON array of account IDs for scope modification.
    *   **Value Example**: `["123456789012"]`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{regions_scope_enabled}}`:
    *   **Description**: Flag to enable region scope modifications.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{regions_scope_type}}`:
    *   **Description**: Type of region scope modification (INCLUDE or EXCLUDE).
    *   **Value Example**: `"INCLUDE"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{scope_regions_array}}`:
    *   **Description**: JSON array of regions for scope modification.
    *   **Value Example**: `["us-east-1", "us-west-2"]`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{xsiam_analytics_enabled}}`:
    *   **Description**: Flag to enable XSIAM analytics capability.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{dspm_enabled}}`:
    *   **Description**: Flag to enable Data Security Posture Management capability.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{registry_scanning_enabled}}`:
    *   **Description**: Flag to enable registry scanning capability.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{registry_scan_type}}`:
    *   **Description**: Type of registry scanning (e.g., ECR, ACR, GAR).
    *   **Value Example**: `"ECR"`
    *   **Used In APIs**:
        *   Create a cloud onboarding integration template
        *   Edit the specified integration instance template
*   `{{instance_ids_to_delete_array}}`:
    *   **Description**: JSON array of instance IDs to delete.
    *   **Value Example**: `["instance-1", "instance-2"]`
    *   **Used In APIs**:
        *   Delete the specified integration instances
*   `{{scan_env_id}}`:
    *   **Description**: Scan environment ID for editing an instance.
    *   **Value Example**: `"YOUR_SCAN_ENV_ID"`
    *   **Used In APIs**:
        *   Edit the specified integration instance template
*   `{{updated_instance_name}}`:
    *   **Description**: New name when editing an instance.
    *   **Value Example**: `"My Updated Instance"`
    *   **Used In APIs**:
        *   Edit the specified integration instance template
*   `{{instance_ids_to_toggle_array}}`:
    *   **Description**: JSON array of instance IDs to enable or disable.
    *   **Value Example**: `["e22b3a29260c404183d1a0ea6cbd4418", "d32d3b19730d414387d2a3ea7eac4218"]`
    *   **Used In APIs**:
        *   Enable or disable cloud integration instance
*   `{{enable_instance_flag}}`:
    *   **Description**: Flag to enable (true) or disable (false) instances.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Enable or disable cloud integration instance
*   `{{get_instances_sort_field}}`:
    *   **Description**: Field to sort by when getting instances (e.g., STATUS, NAME).
    *   **Value Example**: `"STATUS"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_sort_order}}`:
    *   **Description**: Sort order (ASC or DESC) when getting instances.
    *   **Value Example**: `"DESC"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_paging_from}}`:
    *   **Description**: Starting index for pagination when getting instances.
    *   **Value Example**: `"0"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_paging_to}}`:
    *   **Description**: Ending index for pagination when getting instances.
    *   **Value Example**: `"50"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_filter_field_csp}}`:
    *   **Description**: Field to filter on when getting instances (e.g., CLOUD_PROVIDER).
    *   **Value Example**: `"CLOUD_PROVIDER"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_filter_type_csp}}`:
    *   **Description**: Filter type (e.g., EQ, NEQ) when getting instances.
    *   **Value Example**: `"EQ"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances
*   `{{get_instances_filter_value_csp}}`:
    *   **Description**: Value to filter by when getting instances (e.g., AWS).
    *   **Value Example**: `"AWS"`
    *   **Used In APIs**:
        *   Get all or filtered integration instances

### Outposts APIs

*   `{{outpost_tf_download_url}}`:
    *   **Description**: URL for downloading the Terraform template for an outpost.
    *   **Value Example**: `"YOUR_OUTPOST_TF_DOWNLOAD_URL"`
    *   **Used In APIs**:
        *   Edit an outpost template

### Application Security - Integrations APIs

*   `{{external_projects_array}}`:
    *   **Description**: JSON array of external project details for AppSec integration updates.
    *   **Value Example**: `[{"externalBranchName": "main", "repoId": "repo1", "externalProjectId": "proj1", "branchName": "develop", "externalId": "ext1"}]`
    *   **Used In APIs**:
        *   Update an AppSec integration
*   `{{integration_states_array}}`:
    *   **Description**: JSON array of states for AppSec integration updates.
    *   **Value Example**: `["active", "pending"]`
    *   **Used In APIs**:
        *   Update an AppSec integration

### Application Security - Policies APIs

*   `{{scan_cas_license_enabled}}`:
    *   **Description**: Flag to enable CAS License Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_operational_risk_enabled}}`:
    *   **Description**: Flag to enable CAS Operational Risk Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_third_party_weaknesses_enabled}}`:
    *   **Description**: Flag to enable CAS Third Party Weaknesses scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_ci_cd_risk_enabled}}`:
    *   **Description**: Flag to enable CAS CI/CD Risk Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_secret_enabled}}`:
    *   **Description**: Flag to enable CAS Secret Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_cve_enabled}}`:
    *   **Description**: Flag to enable CAS CVE Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{scan_cas_iac_enabled}}`:
    *   **Description**: Flag to enable CAS IaC Scanner for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{dev_suppression_affects}}`:
    *   **Description**: Flag indicating if developer suppression affects the AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{policy_scope_object}}`:
    *   **Description**: JSON object defining the scope for the AppSec policy.
    *   **Value Example**: `{"SEARCH_FIELD": "TAG_KEY", "SEARCH_TYPE": "EQ", "SEARCH_VALUE": "environment"}`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{policy_name}}`:
    *   **Description**: Name for the AppSec policy.
    *   **Value Example**: `"My AppSec Policy"`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{policy_description}}`:
    *   **Description**: Description for the AppSec policy.
    *   **Value Example**: `"Default AppSec policy"`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{trigger_pr_enabled}}`:
    *   **Description**: Flag to enable PR trigger for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{trigger_periodic_enabled}}`:
    *   **Description**: Flag to enable periodic trigger for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{trigger_cicd_enabled}}`:
    *   **Description**: Flag to enable CI/CD trigger for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{policy_conditions_object}}`:
    *   **Description**: JSON object defining the conditions for the AppSec policy.
    *   **Value Example**: `{"SEARCH_FIELD": "Severity", "SEARCH_TYPE": "EQ", "SEARCH_VALUE": "CRITICAL"}`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{action_report_issue_enabled}}`:
    *   **Description**: Flag to enable 'reportIssue' action for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{action_block_pr_enabled}}`:
    *   **Description**: Flag to enable 'blockPr' action for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{action_block_cicd_enabled}}`:
    *   **Description**: Flag to enable 'blockCicd' action for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{action_report_pr_comment_enabled}}`:
    *   **Description**: Flag to enable 'reportPrComment' action for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{action_report_cicd_enabled}}`:
    *   **Description**: Flag to enable 'reportCicd' action for AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy
*   `{{policy_enabled}}`:
    *   **Description**: Flag to enable or disable the AppSec policy.
    *   **Value Example**: `true`
    *   **Used In APIs**:
        *   Create an AppSec policy

## Modifying Variables

To use this collection:
1.  Fork the collection to your Postman workspace.
2.  Select the collection.
3.  Go to the "Variables" tab.
4.  Update the "CURRENT VALUE" for each variable as needed for your environment and specific API calls. The "INITIAL VALUE" often contains an example or placeholder.

This approach ensures that sensitive information (like API keys) and frequently changing parameters (like instance IDs or names) are managed centrally and not hardcoded into each request.
