# REST API endpoints for Copilot cloud agent repository management

Use the REST API to manage repository-level settings for Copilot cloud agent.


> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.


## Get Copilot cloud agent configuration for a repository

```
GET /repos/{owner}/{repo}/copilot/cloud-agent/configuration
```

Note

This endpoint is in public preview and is subject to change.

Gets the Copilot cloud agent configuration for a repository, including MCP server
configuration, enabled review tools, Actions workflow approval settings, and firewall
configuration.
OAuth app tokens and personal access tokens (classic) need the repo scope to use this endpoint.


### Parameters


#### Headers


- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.



#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.






### HTTP response status codes


- **200** - OK


- **401** - Requires authentication


- **403** - Forbidden


- **404** - Resource not found


- **500** - Internal Error




### Code examples



#### Example 1: Status Code 200

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/copilot/cloud-agent/configuration
```

**Response schema (Status: 200):**

* `mcp_configuration`: required, object or null, additional properties allowed
* `enabled_tools`: required, object:
  * `codeql`: required, boolean
  * `copilot_code_review`: required, boolean
  * `secret_scanning`: required, boolean
  * `dependency_vulnerability_checks`: required, boolean
* `require_actions_workflow_approval`: required, boolean
* `is_firewall_enabled`: required, boolean
* `is_firewall_recommended_allowlist_enabled`: required, boolean
* `custom_allowlist`: required, array of string



#### Example 2: Status Code 200

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/copilot/cloud-agent/configuration
```

**Response schema (Status: 200):**

* `mcp_configuration`: required, object or null, additional properties allowed
* `enabled_tools`: required, object:
  * `codeql`: required, boolean
  * `copilot_code_review`: required, boolean
  * `secret_scanning`: required, boolean
  * `dependency_vulnerability_checks`: required, boolean
* `require_actions_workflow_approval`: required, boolean
* `is_firewall_enabled`: required, boolean
* `is_firewall_recommended_allowlist_enabled`: required, boolean
* `custom_allowlist`: required, array of string