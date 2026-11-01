# Make It Lean

让自主推进、持续整理和完整交付成为同一项工作。适用于软件开发、论文复现、实验、文档及其他产出型项目。

**承接已有成果，沿既定目标与路线推进。** Lean 指减少无效工作、存量冗余和流程负担，适用于不同规模的项目。

## 它带来的工作方式

- 主动调查、修复和验证能够解决的问题，推进到实际交付。
- 操作与实际需要相称：检查解决具体问题，已有结果适用就复用，足够支撑交付后及时结束。
- 按真实用途判断历史文件与临时产物的价值，用完及时整理。
- 固定主文档目录，优先原位更新，减少计划、提示词和交接副本。
- 交付说明已确认的结果、实际验证和产物入口。
- 沟通使用具体动作与结果，减少流程宣告和笼统的防御性声明，简明说明影响使用的实际限制。
- 普通任务沿用合适分支，按已有授权同步；未使用 Git 的项目直接交付文件，用户明确要求后才启用 Git。
- 单个对话即可完成全流程，长任务和协作按实际需要安排。

## 安装

将仓库克隆到个人技能目录。若已有同名安装，先核对差异并更新原目录，保持一个权威版本。

Windows PowerShell：

```powershell
$leanSkillsRoot = Join-Path $env:USERPROFILE '.agents\skills'
New-Item -ItemType Directory -Path $leanSkillsRoot -Force | Out-Null
git clone https://github.com/indulge-gif/make-it-lean.git (Join-Path $leanSkillsRoot 'make-it-lean')
```

macOS / Linux：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/indulge-gif/make-it-lean.git ~/.agents/skills/make-it-lean
```

团队也可将技能文件放入项目的 `.agents/skills/make-it-lean/`。其他 agent 工具可按其技能目录约定安装，或读取 [SKILL.md](SKILL.md)。

## 使用

在新对话中输入：

```text
使用 $make-it-lean，承接本项目已有成果，沿既定目标和路线完成〔任务〕。
```

支持新项目建立约定、现有项目精简和持续开发。具体操作沿用用户授权与目标项目约定。

## 内容

- [技能入口](SKILL.md)：最高原则、执行责任、文档、验证与 Git 规则。
- [项目建立与存量整理](references/project-adoption.md)：采用方式与文件价值判断。
- [接续与可选协作](references/collaboration.md)：新想法、反馈、交接和简短提示词。
- [构建与复用说明](docs/构建与复用说明.md)：完整结构、设计、安装、维护和样例验证记录。

`agents/openai.yaml` 提供 Codex 界面元数据。本技能不依赖运行脚本、MCP 或 API key。
