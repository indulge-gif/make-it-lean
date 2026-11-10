# Make It Lean

[中文](README.md) | English

Bring autonomous progress, ongoing cleanup, and complete delivery into the same workflow. A skill for software development, research reproductions, experiments, documentation, and other projects that produce deliverables.

**Build on existing work and follow the project's agreed goals and direction.** Lean means reducing wasted effort, accumulated clutter, and process overhead, at any project size.

The skill instructions and supporting documents are currently primarily in Chinese. This README provides English installation and usage guidance.

## How it guides the work

- Investigate, fix, and verify problems the agent can resolve, and carry the task through to delivery.
- Keep operations proportional to the task: use checks to answer specific questions, reuse results that still apply, and stop when the evidence is sufficient for delivery.
- Judge historical files and temporary artifacts by their actual use, and tidy them when their purpose is complete.
- Move files to the system recycle bin by default. Permanent deletion requires explicit user authorization; if recycling fails or is unavailable, keep the affected files instead of falling back to permanent deletion.
- Maintain one main documentation directory, update existing documents first, and avoid redundant plans, prompts, and handoff copies.
- Report confirmed results, the verification actually performed, and where to find the deliverables.
- Communicate concrete actions and results. Avoid process announcements and vague defensive statements; briefly explain limitations that affect use.
- Use an existing suitable Git branch for ordinary tasks and synchronize only within the user's authorization. Deliver files directly for projects without Git; initialize Git only when explicitly requested.
- Complete the workflow in one conversation when practical. Arrange handoffs or collaboration when the task calls for them.

## Installation

Clone the repository into your agent's personal skills directory. If the skill is already installed, compare the versions and update the existing directory to keep one authoritative installation.

### Codex

Windows PowerShell:

```powershell
$leanSkillsRoot = Join-Path $env:USERPROFILE '.agents\skills'
New-Item -ItemType Directory -Path $leanSkillsRoot -Force | Out-Null
git clone https://github.com/indulge-gif/make-it-lean.git (Join-Path $leanSkillsRoot 'make-it-lean')
```

macOS / Linux:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/indulge-gif/make-it-lean.git ~/.agents/skills/make-it-lean
```

### Claude Code

Windows PowerShell:

```powershell
$leanSkillsRoot = Join-Path $env:USERPROFILE '.claude\skills'
New-Item -ItemType Directory -Path $leanSkillsRoot -Force | Out-Null
git clone https://github.com/indulge-gif/make-it-lean.git (Join-Path $leanSkillsRoot 'make-it-lean')
```

macOS / Linux:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/indulge-gif/make-it-lean.git ~/.claude/skills/make-it-lean
```

Claude Code uses `SKILL.md` and reads referenced supporting files as needed. `agents/openai.yaml` provides Codex interface metadata; Claude Code does not require it.

### Project sharing and other agents

Teams can place the complete skill directory in their project's skills directory: `.agents/skills/make-it-lean/` for Codex, or `.claude/skills/make-it-lean/` for Claude Code. For other agents, use the tool's supported location for skills or have it read [SKILL.md](SKILL.md).

## Usage

In a new Codex conversation, enter:

```text
Use $make-it-lean to build on this project's existing work and complete [task] within its agreed goals and direction.
```

In Claude Code, invoke the skill with a slash command followed by the task:

```text
/make-it-lean Build on this project's existing work and complete [task] within its agreed goals and direction.
```

Use it to establish conventions for a new project, streamline an existing project, or continue ongoing development. Actions remain subject to the user's authorization and the target project's conventions. Installing the skill does not authorize external publishing or Git synchronization.

## Contents

- [Skill entry point](SKILL.md): guiding principle, execution responsibilities, documentation, verification, and Git conventions.
- [Project adoption and cleanup](references/project-adoption.md): adoption approaches and criteria for judging file value.
- [Continuity and optional collaboration](references/collaboration.md): new ideas, feedback, handoffs, and concise task prompts.
- [Build and reuse guide](docs/构建与复用说明.md): structure, design, installation, maintenance, and recorded example checks.

`agents/openai.yaml` supplies Codex interface metadata. The skill itself does not require runtime scripts, an MCP connection, or an API key; the agent needs the tools required by the actual task.

## License

Licensed under the [MIT License](LICENSE).
