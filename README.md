# Hugging Bay for coding agents

Your agent finds an open model that fits your machine and gets the exact file, with size and SHA-256. No account, no key.

## Install

Every agent on this machine, one command:

```sh
npx hugging-bay-agents setup
```

Or pick one.

**Claude Code**

```
/plugin marketplace add barneywohl/hugging-bay-agents
/plugin install hugging-bay@hugging-bay
```

**Codex**

```sh
codex mcp add hugging-bay --url "https://huggingbay.xyz/api/mcp?profile=agent&src=pack-codex"
mkdir -p ~/.agents/skills/hugging-bay-local-models
curl -fsSL https://raw.githubusercontent.com/barneywohl/hugging-bay-agents/main/codex/skills/hugging-bay-local-models/SKILL.md -o ~/.agents/skills/hugging-bay-local-models/SKILL.md
```

**Cursor**

[Add the MCP server](cursor://anysphere.cursor-deeplink/mcp/install?name=hugging-bay&config=eyJ1cmwiOiJodHRwczovL2h1Z2dpbmdiYXkueHl6L2FwaS9tY3A%2FcHJvZmlsZT1hZ2VudCZzcmM9cGFjay1jdXJzb3IifQ%3D%3D), then copy `cursor/rules/hugging-bay.mdc` into your repo's `.cursor/rules/`.

**VS Code**

[Add the MCP server](vscode:mcp/install?%7B%22name%22%3A%22hugging-bay%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fhuggingbay.xyz%2Fapi%2Fmcp%3Fprofile%3Dagent%26src%3Dpack-vscode%22%7D)

**Any agent that reads AGENTS.md**

Paste `AGENTS.snippet.md` into your repo's `AGENTS.md`, or run `npx hugging-bay-agents setup --project`.

## Try it

Ask your agent: "Find a chat model that fits this machine and download it."

## Pin the model in your repo

```sh
npx hugging-bay-agents pin --model <owner/repo> --file <path> --sha256 <hex> --id <artifact-id>
npx hugging-bay-agents verify
```

`hb.lock` records the model, file and SHA-256, so the next person or agent gets the same bytes.

## What is inside

| Path | For |
| --- | --- |
| `.claude-plugin/marketplace.json`, `plugins/hugging-bay/` | Claude Code plugin: MCP server and the `local-models` skill |
| `codex/skills/hugging-bay-local-models/SKILL.md` | Codex skill |
| `cursor/rules/hugging-bay.mdc` | Cursor rule |
| `AGENTS.snippet.md` | Block for AGENTS.md |

A matching SHA-256 shows the bytes arrived unchanged. It does not show that a model runs or that its license fits your use.

Docs: https://huggingbay.xyz/docs/for-agents.md. MIT license.
