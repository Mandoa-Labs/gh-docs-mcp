# Copilot

Reference documentation for GraphQL schema types in the Copilot category.

## Agentic - interface

Copilot Agentic fields in context of the current viewer.

### Fields for `Agentic`

* `viewerCopilotAgentCreatesChannel` (String): Channel value for subscribing to live updates for session creations.
* `viewerCopilotAgentLogUpdatesChannel` (String): Channel value for subscribing to live updates for session log updates.
* `viewerCopilotAgentTaskUpdatesChannel` (String): Channel value for subscribing to live updates for task updates.
* `viewerCopilotAgentUpdatesChannel` (String): Channel value for subscribing to live updates for session updates.

### Implemented by

* User

## CopilotEndpoints - object

Copilot endpoint information.

### Fields for `CopilotEndpoints`

* `api` (String!): Copilot API endpoint.
* `originTracker` (String!): Copilot origin tracker endpoint.
* `proxy` (String!): Copilot proxy endpoint.
* `telemetry` (String!): Copilot telemetry endpoint.