# vscode-agents

A small repository of custom VS Code Copilot agents and helper scripts for managing them.

## Overview

This workspace contains custom Copilot agent definitions in Markdown format. Each agent file defines:

- `name`: the agent identifier
- `description`: a short summary of the agent's purpose
- `tools`: the set of VS Code Copilot tools the agent is allowed to use

## Agents

- `basic.agent.md`
  - A lightweight agent with access to basic file-related tools such as reading files, creating files/directories, editing files, renaming files, and searching.

- `read.agent.md`
  - A read-only agent with access to file and workspace inspection tools, including search and terminal context, but without edit or execution privileges.

- `write.agent.md`
  - A write-enabled agent with broad access to edit tools, terminal execution tools, and search.

- `none.agent.md`
  - A restricted agent with no tool access.

## Usage

Use the provided npm scripts to sync agent definitions with your local Copilot agents folder.

### Push agents to Copilot

```bash
npm run push
```

This copies all `*.agent.md` files from this repository into `~/.copilot/agents/`.

### Pull agents from Copilot

```bash
npm run pull
```

This copies all agent files currently in `~/.copilot/agents/` into this repository.

## Package scripts

- `pull`: synchronize agent files from `~/.copilot/agents/` into this repository.
- `push`: synchronize repository agent files into `~/.copilot/agents/`.
- `version`: updates the package version using the installed `code` executable version string.

## Notes

- The repository is intentionally minimal and focuses on agent configuration files.
- Make sure your Copilot installation uses `~/.copilot/agents/` for custom agent storage before running push/pull scripts.
