# Custom skills

Skills are reusable prompt modules that extend Copilot's capabilities. Load skills from directories to give Copilot specialized abilities for specific domains or workflows.

<!-- markdownlint-disable GHD046 GHD005 -->

<!-- Suppressed: GHD046 (outdated release terminology), GHD005 (hardcoded data variable) -->

## Overview

A skill is a named directory containing a `SKILL.md` file—a markdown document that provides instructions to Copilot. When loaded, the skill's content is injected into the session context.

Skills allow you to:

* Package domain expertise into reusable modules
* Share specialized behaviors across projects
* Organize complex agent configurations
* Enable/disable capabilities per session

## Loading skills

Specify directories containing skills when creating a session:

<div class="ghd-codetabs">
<div class="ghd-codetab" data-lang="typescript" data-label="TypeScript"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">TypeScript</div>

```typescript
import { CopilotClient } from "@github/copilot-sdk";

const client = new CopilotClient();
const session = await client.createSession({
    model: "gpt-4.1",
    skillDirectories: [
        "./skills/code-review",
        "./skills/documentation",
    ],
    onPermissionRequest: async () => ({ kind: "approve-once" }),
});

// Copilot now has access to skills in those directories
await session.sendAndWait({ prompt: "Review this code for security issues" });
```

</div>

<div class="ghd-codetab" data-lang="python" data-label="Python"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Python</div>

```python
from copilot import CopilotClient, PermissionDecisionApproveOnce

async def main():
    client = CopilotClient()
    await client.start()

    session = await client.create_session(
        on_permission_request=lambda req, inv: PermissionDecisionApproveOnce(),
        model="gpt-4.1",
        skill_directories=[
            "./skills/code-review",
            "./skills/documentation",
        ],
    )

    # Copilot now has access to skills in those directories
    await session.send_and_wait("Review this code for security issues")

    await client.stop()
```

</div>

<div class="ghd-codetab" data-lang="go" data-label="Go"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Go</div>

```golang
package main

import (
    "context"
    "log"
    copilot "github.com/github/copilot-sdk/go"
    "github.com/github/copilot-sdk/go/rpc"
)

func main() {
    ctx := context.Background()
    client := copilot.NewClient(nil)
    if err := client.Start(ctx); err != nil {
        log.Fatal(err)
    }
    defer client.Stop()

    session, err := client.CreateSession(ctx, &copilot.SessionConfig{
        Model: "gpt-4.1",
        SkillDirectories: []string{
            "./skills/code-review",
            "./skills/documentation",
        },
        OnPermissionRequest: func(req copilot.PermissionRequest, inv copilot.PermissionInvocation) (rpc.PermissionDecision, error) {
            return &rpc.PermissionDecisionApproveOnce{}, nil
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    // Copilot now has access to skills in those directories
    _, err = session.SendAndWait(ctx, copilot.MessageOptions{
        Prompt: "Review this code for security issues",
    })
    if err != nil {
        log.Fatal(err)
    }
}
```

</div>

<div class="ghd-codetab" data-lang="dotnet" data-label=".NET"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">.NET</div>

```csharp
using GitHub.Copilot;
using GitHub.Copilot.Rpc;

await using var client = new CopilotClient();
await using var session = await client.CreateSessionAsync(new SessionConfig
{
    Model = "gpt-4.1",
    SkillDirectories = new List<string>
    {
        "./skills/code-review",
        "./skills/documentation",
    },
    OnPermissionRequest = (req, inv) =>
        Task.FromResult(PermissionDecision.ApproveOnce()),
});

// Copilot now has access to skills in those directories
await session.SendAndWaitAsync(new MessageOptions
{
    Prompt = "Review this code for security issues"
});
```

</div>

<div class="ghd-codetab" data-lang="java" data-label="Java"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Java</div>

```java
import com.github.copilot.sdk.CopilotClient;
import com.github.copilot.sdk.events.*;
import com.github.copilot.sdk.json.*;
import java.util.List;

try (var client = new CopilotClient()) {
    client.start().get();

    var session = client.createSession(
        new SessionConfig()
            .setModel("gpt-4.1")
            .setSkillDirectories(List.of(
                "./skills/code-review",
                "./skills/documentation"
            ))
            .setOnPermissionRequest(PermissionHandler.APPROVE_ALL)
    ).get();

    // Copilot now has access to skills in those directories
    session.sendAndWait(new MessageOptions()
        .setPrompt("Review this code for security issues")
    ).get();
}
```

</div>

</div>

## Disabling skills

Disable specific skills while keeping others active:

<div class="ghd-codetabs">
<div class="ghd-codetab" data-lang="typescript" data-label="TypeScript"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">TypeScript</div>

```typescript
const session = await client.createSession({
    skillDirectories: ["./skills"],
    disabledSkills: ["experimental-feature", "deprecated-tool"],
});
```

</div>

<div class="ghd-codetab" data-lang="python" data-label="Python"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Python</div>

```python
from copilot.session import PermissionHandler

session = await client.create_session(
    on_permission_request=PermissionHandler.approve_all,
    skill_directories=["./skills"],
    disabled_skills=["experimental-feature", "deprecated-tool"],
)
```

</div>

<div class="ghd-codetab" data-lang="go" data-label="Go"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Go</div>

```golang
package main

import (
	"context"
	copilot "github.com/github/copilot-sdk/go"
	"github.com/github/copilot-sdk/go/rpc"
)

func main() {
	ctx := context.Background()
	client := copilot.NewClient(nil)

	session, _ := client.CreateSession(ctx, &copilot.SessionConfig{
		SkillDirectories: []string{"./skills"},
		DisabledSkills:   []string{"experimental-feature", "deprecated-tool"},
		OnPermissionRequest: func(req copilot.PermissionRequest, inv copilot.PermissionInvocation) (rpc.PermissionDecision, error) {
			return &rpc.PermissionDecisionApproveOnce{}, nil
		},
	})
	_ = session
}
```

```golang
session, _ := client.CreateSession(context.Background(), &copilot.SessionConfig{
    SkillDirectories: []string{"./skills"},
    DisabledSkills:   []string{"experimental-feature", "deprecated-tool"},
})
```

</div>

<div class="ghd-codetab" data-lang="dotnet" data-label=".NET"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">.NET</div>

```csharp
using GitHub.Copilot;
using GitHub.Copilot.Rpc;

public static class SkillsExample
{
    public static async Task Main()
    {
        await using var client = new CopilotClient();

        var session = await client.CreateSessionAsync(new SessionConfig
        {
            SkillDirectories = new List<string> { "./skills" },
            DisabledSkills = new List<string> { "experimental-feature", "deprecated-tool" },
            OnPermissionRequest = (req, inv) =>
                Task.FromResult(PermissionDecision.ApproveOnce()),
        });
    }
}
```

```csharp
var session = await client.CreateSessionAsync(new SessionConfig
{
    SkillDirectories = new List<string> { "./skills" },
    DisabledSkills = new List<string> { "experimental-feature", "deprecated-tool" },
});
```

</div>

<div class="ghd-codetab" data-lang="java" data-label="Java"><div class="ghd-codetab-fallback-label" role="heading" aria-level="3">Java</div>

```java
import com.github.copilot.sdk.json.*;
import java.util.List;

var session = client.createSession(
    new SessionConfig()
        .setSkillDirectories(List.of("./skills"))
        .setDisabledSkills(List.of("experimental-feature", "deprecated-tool"))
        .setOnPermissionRequest(PermissionHandler.APPROVE_ALL)
).get();
```

</div>

</div>

## Skill directory structure

Each skill is a named subdirectory containing a `SKILL.md` file:

```text
skills/
├── code-review/
│   └── SKILL.md
└── documentation/
    └── SKILL.md
```

The `skillDirectories` option points to the parent directory (e.g., `./skills`). The CLI discovers all `SKILL.md` files in immediate subdirectories.

### SKILL.md format

A `SKILL.md` file is a markdown document with optional YAML frontmatter:

```markdown
---
name: code-review
description: Specialized code review capabilities
---

# Code Review Guidelines

When reviewing code, always check for:

1. **Security vulnerabilities** - SQL injection, XSS, etc.
2. **Performance issues** - N+1 queries, memory leaks
3. **Code style** - Consistent formatting, naming conventions
4. **Test coverage** - Are critical paths tested?

Provide specific line-number references and suggested fixes.
```

The frontmatter fields:

* **`name`**: The skill's identifier (used with `disabledSkills` to selectively disable it). If omitted, the directory name is used.
* **`description`**: A short description of what the skill does.

The markdown body contains the instructions that are injected into the session context when the skill is loaded.

## Configuration options

### SessionConfig skill fields

| Language | Field               | Type           | Description                     |
| -------- | ------------------- | -------------- | ------------------------------- |
| Node.js  | `skillDirectories`  | `string[]`     | Directories to load skills from |
| Node.js  | `disabledSkills`    | `string[]`     | Skills to disable               |
| Python   | `skill_directories` | `list[str]`    | Directories to load skills from |
| Python   | `disabled_skills`   | `list[str]`    | Skills to disable               |
| Go       | `SkillDirectories`  | `[]string`     | Directories to load skills from |
| Go       | `DisabledSkills`    | `[]string`     | Skills to disable               |
| .NET     | `SkillDirectories`  | `List<string>` | Directories to load skills from |
| .NET     | `DisabledSkills`    | `List<string>` | Skills to disable               |

## Best practices

1. **Organize by domain** - Group related skills together (e.g., `skills/security/`, `skills/testing/`)

2. **Use frontmatter** - Include `name` and `description` in YAML frontmatter for clarity

3. **Document dependencies** - Note any tools or MCP servers a skill requires

4. **Test skills in isolation** - Verify skills work before combining them

5. **Use relative paths** - Keep skills portable across environments

## Combining with other features

### Skills + custom agents

Skills listed in an agent's `skills` field are **eagerly preloaded**—their full content is injected into the agent's context at startup, so the agent has access to the skill instructions immediately without needing to invoke a skill tool. Skill names are resolved from the session-level `skillDirectories`.

```typescript
const session = await client.createSession({
    skillDirectories: ["./skills/security"],
    customAgents: [{
        name: "security-auditor",
        description: "Security-focused code reviewer",
        prompt: "Focus on OWASP Top 10 vulnerabilities",
        skills: ["security-scan", "dependency-check"],
    }],
    onPermissionRequest: async () => ({ kind: "approve-once" }),
});
```

> \[!NOTE]
> Skills are opt-in—when `skills` is omitted, no skill content is injected. Sub-agents do not inherit skills from the parent; you must list them explicitly per agent.

### Skills + MCP servers

Skills can complement MCP server capabilities:

```typescript
const session = await client.createSession({
    skillDirectories: ["./skills/database"],
    mcpServers: {
        postgres: {
            type: "local",
            command: "npx",
            args: ["-y", "@modelcontextprotocol/server-postgres"],
            tools: ["*"],
        },
    },
    onPermissionRequest: async () => ({ kind: "approve-once" }),
});
```

## Troubleshooting

### Skills not loading

1. **Check path exists** - Verify the skill directory path is correct and contains subdirectories with `SKILL.md` files
2. **Check permissions** - Ensure the SDK can read the directory
3. **Check SKILL.md format** - Verify the markdown is well-formed and any YAML frontmatter uses valid syntax
4. **Enable debug logging** - Set `logLevel: "debug"` to see skill loading logs

### Skill conflicts

If multiple skills provide conflicting instructions:

* Use `disabledSkills` to exclude conflicting skills
* Reorganize skill directories to avoid overlaps

## See also

* [Build your first Copilot-powered app](/en/copilot/how-tos/copilot-sdk/getting-started#create-custom-agents) - Define specialized AI personas
* [Build your first Copilot-powered app](/en/copilot/how-tos/copilot-sdk/getting-started#step-4-add-a-custom-tool) - Build your own tools
* [Using MCP servers with the GitHub Copilot SDK](/en/copilot/how-tos/copilot-sdk/features/mcp) - Connect external tool providers