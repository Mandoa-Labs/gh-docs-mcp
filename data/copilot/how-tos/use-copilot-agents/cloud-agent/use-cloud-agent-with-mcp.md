# Using Copilot cloud agent via the GitHub MCP Server

Start Copilot cloud agent sessions from any IDE or agentic tool that supports Model Context Protocol (MCP).

> \[!NOTE]
>
> * This capability is only available on the remote GitHub MCP Server and host applications where remote MCP Servers are supported.

## Starting a session

1. Install the GitHub MCP Server in your preferred IDE or agentic coding tool. See [Using the GitHub MCP Server in your IDE](/en/copilot/how-tos/context/model-context-protocol/using-the-github-mcp-server).

2. Ensure the `create_pull_request_with_copilot` tool is enabled.

3. Open chat.

4. Type a prompt asking Copilot to create a pull request, with the details of what you want to change.

   For example, `Open a PR in my repository to expand unit test coverage.`

   > \[!TIP]
   >
   > * You can ask Copilot to open a pull request using a specific branch as the base branch by including it in your prompt.

5. Submit your prompt.

   Copilot will start a new session, open a draft pull request and work on the task in the background. As it works, it will push changes to the pull request, and once it has finished, it will add you as a reviewer. In most cases, the MCP host will show you the URL of the created pull request.

## Further reading

* [Managing agent sessions](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/manage-and-track-agents)
* [Best practices for using GitHub Copilot to work on tasks](/en/copilot/tutorials/cloud-agent/get-the-best-results)