<div align="center">

# Awesome ACP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<img src="https://zed.dev/img/acp/banner-dark.webp" alt="Agent Client Protocol" width="640">

**A curated list of everything in the [Agent Client Protocol (ACP)](https://agentclientprotocol.com) ecosystem — the open standard that connects any code editor to any AI agent.**

[Protocol](https://github.com/agentclientprotocol/agent-client-protocol) ·
[Docs](https://agentclientprotocol.com) ·
[Registry](https://github.com/agentclientprotocol/registry) ·
[Live Protocol Matrix](https://github.com/agentclientprotocol/registry/blob/main/.protocol-matrix/latest.md)

</div>

---

> **What is ACP?**
> The **Agent Client Protocol (ACP)** standardizes communication between *code editors* (and other UIs) and *AI coding agents*. It is to agents what the Language Server Protocol (LSP) is to language tooling: implement it once, and any ACP client can drive any ACP agent over a simple JSON-RPC stream. It was introduced by [Zed](https://zed.dev/blog/bring-your-own-agent-to-zed) and is now developed in the open at [agentclientprotocol.com](https://agentclientprotocol.com).

> [!IMPORTANT]
> **"ACP" is overloaded.** This list covers the **Agent _Client_ Protocol** (editor ↔ agent, by Zed). It is **not** the [Agent Communication Protocol](https://agentcommunicationprotocol.dev) (IBM/BeeAI, agent ↔ agent) nor the [Agentic Commerce Protocol](https://www.agenticcommerce.dev) (OpenAI/Stripe, checkout). See [Related Protocols](#related-protocols).

## Contents

- [The Protocol](#the-protocol)
- [Official SDKs](#official-sdks)
- [Community Libraries & SDKs](#community-libraries--sdks)
- [Editors & IDEs](#editors--ides)
- [Desktop & Web Clients](#desktop--web-clients)
- [Terminal & TUI Clients](#terminal--tui-clients)
- [Mobile & Remote Control](#mobile--remote-control)
- [Chat & Messaging Bridges](#chat--messaging-bridges)
- [Coding Agents](#coding-agents)
- [Agent Bridges & Adapters](#agent-bridges--adapters)
- [Orchestrators & Multi-Agent Managers](#orchestrators--multi-agent-managers)
- [Beyond Coding — Personal, Domain & Data Agents](#beyond-coding--personal-domain--data-agents)
- [Developer Tools & Utilities](#developer-tools--utilities)
- [Examples & Templates](#examples--templates)
- [Articles, Talks & Guides](#articles-talks--guides)
- [Related Protocols](#related-protocols)
- [Contributing](#contributing)

## The Protocol

The canonical specification, schema, and reference resources.

- [agent-client-protocol](https://github.com/agentclientprotocol/agent-client-protocol) — The protocol specification, JSON Schema, and reference Rust crate. *"A protocol for connecting any editor to any agent."*
- [agentclientprotocol.com](https://agentclientprotocol.com) — Official documentation: [agents](https://agentclientprotocol.com/overview/agents), [clients](https://agentclientprotocol.com/overview/clients), and [community libraries](https://agentclientprotocol.com/libraries/community).
- [registry](https://github.com/agentclientprotocol/registry) — Official, CI-verified registry of ACP agents. Served at `https://cdn.agentclientprotocol.com/registry/v1/latest/registry.json`.
- [Protocol Adaptation Matrix](https://github.com/agentclientprotocol/registry/blob/main/.protocol-matrix/latest.md) — Auto-generated daily report probing every registered agent for `initialize`, auth methods, and supported capabilities (`session/list`, `session/fork`, `session/resume`, …).
- [JSON Schema (v1)](https://github.com/agentclientprotocol/agent-client-protocol/blob/main/schema/v1/schema.json) — The wire format definition.
- [symposium-acp](https://github.com/agentclientprotocol/symposium-acp) — Reference Symposium implementation of the specification.

## Official SDKs

Maintained under the [`agentclientprotocol`](https://github.com/agentclientprotocol) org.

- [rust-sdk](https://github.com/agentclientprotocol/rust-sdk) — Rust SDK for clients and agents ([`agent-client-protocol` on crates.io](https://crates.io/crates/agent-client-protocol)).
- [typescript-sdk](https://github.com/agentclientprotocol/typescript-sdk) — TypeScript/JavaScript SDK ([`@agentclientprotocol/sdk`](https://www.npmjs.com/package/@agentclientprotocol/sdk)).
- [python-sdk](https://github.com/agentclientprotocol/python-sdk) — Python SDK for clients and agents.
- [kotlin-sdk](https://github.com/agentclientprotocol/kotlin-sdk) — Kotlin SDK (JVM, more targets in progress).
- [java-sdk](https://github.com/agentclientprotocol/java-sdk) — Java SDK with examples.

## Community Libraries & SDKs

Third-party language bindings and helper libraries.

**Go**
- [coder/acp-go-sdk](https://github.com/coder/acp-go-sdk) — Typed Go SDK with request/response helpers.
- [ironpark/acp-go](https://github.com/ironpark/acp-go) — Go implementation of the protocol.
- [eino-contrib/acp](https://github.com/eino-contrib/acp) — ACP contrib module for the Eino framework.

**Swift**
- [wiedymi/swift-acp](https://github.com/wiedymi/swift-acp) — Swift SDK for ACP.
- [rebornix/acp-swift-sdk](https://github.com/rebornix/acp-swift-sdk) — Swift language SDK.
- [aptove/swift-sdk](https://github.com/aptove/swift-sdk) — Apple-ecosystem Swift SDK.

**.NET / C#**
- [nuskey8/acp-csharp](https://github.com/nuskey8/acp-csharp) — C# SDK for clients and agents.

**Other languages**
- [SkrOYC/acp-dart](https://github.com/SkrOYC/acp-dart) — Dart SDK for ACP.
- [hahwul/acp.cr](https://github.com/hahwul/acp.cr) — Crystal implementation.
- [lostbean/acpex](https://github.com/lostbean/acpex) — Idiomatic Elixir implementation.
- [azmaveth/ex_mcp](https://github.com/azmaveth/ex_mcp) — Elixir MCP + ACP client/server.
- [MagnovaAI/acp-sdk-zig](https://github.com/MagnovaAI/acp-sdk-zig) — Native Zig implementation of the wire protocol.
- [1ay1/acp-cpp](https://github.com/1ay1/acp-cpp) — Modern C++20 implementation.
- [ya-luotao/agent-client-protocol-ruby](https://github.com/ya-luotao/agent-client-protocol-ruby) — Ruby bindings.
- [AgentClientProtocol Vala SDK](https://gitcode.com/ai-outputs/AgentClientProtocol) — Vala implementation.

**Frontend & UI**
- [marimo-team/use-acp](https://github.com/marimo-team/use-acp) — React hooks for connecting to ACP servers.
- [zvzuola/acp-components](https://github.com/zvzuola/acp-components) — UI component library for building ACP front-ends.
- [AcpKit/acp-kit](https://github.com/AcpKit/acp-kit) — Runtime for building applications on top of ACP.

## Editors & IDEs

Native editor integrations and plugins that act as ACP **clients**.

- [Zed](https://zed.dev/docs/ai/external-agents) — The reference client; native support for external ACP agents.
- [JetBrains AI Assistant](https://www.jetbrains.com/help/ai-assistant/acp.html) — Built-in ACP support across IntelliJ IDEA, PyCharm, and the IDE family.
- **Neovim**
  - [olimorris/codecompanion.nvim](https://github.com/olimorris/codecompanion.nvim) — "AI Coding, Vim Style" — the first Neovim ACP client.
  - [carlos-algms/agentic.nvim](https://github.com/carlos-algms/agentic.nvim) — Agentic chat interface with ACP providers.
  - [yetone/avante.nvim](https://github.com/yetone/avante.nvim) — Cursor-like AI IDE experience for Neovim, with ACP support.
  - [brianhuster/acp.nvim](https://github.com/brianhuster/acp.nvim) — A focused ACP client for Neovim.
- **Emacs**
  - [xenodium/agent-shell](https://github.com/xenodium/agent-shell) — Native Emacs buffer for ACP-powered agents.
  - [xenodium/acp.el](https://github.com/xenodium/acp.el) — ACP implementation in Emacs Lisp.
- **VS Code**
  - [formulahendry/vscode-acp](https://github.com/formulahendry/vscode-acp) — Connect to any ACP agent from VS Code.
  - [omercnet/vscode-acp](https://github.com/omercnet/vscode-acp) — Alternative VS Code ACP client.
  - [gayanper/vscode-acp-provider](https://github.com/gayanper/vscode-acp-provider) — ACP provider for VS Code.
- **Obsidian**
  - [RAIT-09/obsidian-agent-client](https://github.com/RAIT-09/obsidian-agent-client) — Bring AI agents into Obsidian via ACP.
  - [WhiskeyJack96/obsidian-agent](https://github.com/WhiskeyJack96/obsidian-agent) — Obsidian plugin with an ACP client implementation.
- **Game engines**
  - [nuskey8/UnityAgentClient](https://github.com/nuskey8/UnityAgentClient) — Integrate any ACP agent into the Unity editor.
  - [3DLabInstruments/UnityACPClient](https://github.com/3DLabInstruments/UnityACPClient) — Unity ACP client plugin.
  - [JasonKim99/AgentGodette](https://github.com/JasonKim99/AgentGodette) — Godot 4 editor plugin for ACP agents.
- **Notebooks & data tools**
  - [wiki3-ai/agent-client-kernel](https://github.com/wiki3-ai/agent-client-kernel) — A Jupyter kernel that speaks ACP.
  - [SchmidtDSE/jupyter-sidekick](https://github.com/SchmidtDSE/jupyter-sidekick) — Jupyter-native access to coding agents over ACP.
- **More**
  - [anandb/nb-complete](https://github.com/anandb/nb-complete) — NetBeans plugin integrating agents over ACP.
  - [eclipse-agents/eclipse-agents](https://github.com/eclipse-agents/eclipse-agents) — Eclipse implementation of MCP and ACP.
  - [Areo-Joe/chrome-acp](https://github.com/Areo-Joe/chrome-acp) — Connect to an ACP agent from the browser.
  - [dweinstein/gtoolkit-acp](https://github.com/dweinstein/gtoolkit-acp) — Glamorous Toolkit (Pharo/Smalltalk) ACP client.
  - [SoFluffyOS/lumide](https://github.com/SoFluffyOS/lumide) — Desktop-first GPU-accelerated code editor built around ACP.

## Desktop & Web Clients

Standalone apps and web UIs for talking to ACP agents.

- [formulahendry/acp-ui](https://github.com/formulahendry/acp-ui) — Modern cross-platform client for ACP.
- [issueye/acp_desktop](https://github.com/issueye/acp_desktop) — Wails-based desktop ACP client.
- [Piebald-AI/gemini-cli-desktop](https://github.com/Piebald-AI/gemini-cli-desktop) — Web/desktop UI for Gemini CLI / Qwen Code.
- [iOfficeAI/AionUi](https://github.com/iOfficeAI/AionUi) — Local, open-source "cowork" desktop app for ACP agents.
- [OpenSource03/harnss](https://github.com/OpenSource03/harnss) — Desktop client/UI to harness Claude Code, Codex, and more.
- [Mng-dev-ai/agentrove](https://github.com/Mng-dev-ai/agentrove) — Self-hosted AI coding workspace for multiple agents.
- [zhzy0077/openagents](https://github.com/zhzy0077/openagents) — Web UI for any ACP-supporting agent.
- [huanyingtianhe/agents-chat](https://github.com/huanyingtianhe/agents-chat) — Standalone multi-agent chat UI for ACP.
- [AnEntrypoint/agentgui](https://github.com/AnEntrypoint/agentgui) — Multi-agent GUI for AI coding assistants.
- [belay-codes/belay](https://github.com/belay-codes/belay) — Desktop client managing connections to AI coding harnesses.
- [Leask/Tabminal](https://github.com/Leask/Tabminal) — Cloud-native terminal and ACP agent workspace.

## Terminal & TUI Clients

- [openclaw/acpx](https://github.com/openclaw/acpx) — Headless CLI client for stateful ACP servers.
- [Toad](https://www.batrachian.ai/) — Universal terminal UI for coding agents over ACP.
- [tilework-tech/nori-cli](https://github.com/tilework-tech/nori-cli) — Simple CLI for working with any ACP agent.
- [dwalleck/cyril](https://github.com/dwalleck/cyril) — Experimental TUI for the ACP ecosystem.
- [one710/codeye](https://github.com/one710/codeye) — Drive Cursor and any ACP agent from your terminal.
- [SDSLeon/lightcode](https://github.com/SDSLeon/lightcode) — One window for all your AI coding agents.
- [fischerf/aar](https://github.com/fischerf/aar) — Coding agent with CLI, TUI, web, and ACP interfaces.

## Mobile & Remote Control

Drive your agents from your phone or across the network.

- [layercodedev/sled](https://github.com/layercodedev/sled) — Teleport Claude Code, Codex, or Gemini CLI to your phone.
- [Eric-Song-Nop/mobvibe](https://github.com/Eric-Song-Nop/mobvibe) — Open Claude Code remote control.
- [rebornix/Agmente](https://github.com/rebornix/Agmente) — iOS client for coding agents via ACP.
- [rcarmo/vibes](https://github.com/rcarmo/vibes) — Mobile-focused chat app to talk to an agent over ACP.
- [arafatamim/Ferngeist](https://github.com/arafatamim/Ferngeist) — Remote-control app for your coding agents.
- [inercia/mitto](https://github.com/inercia/mitto) — Control your AI coding agents on the go (Mac, web, mobile).
- [daniel-farina/grok-remote](https://github.com/daniel-farina/grok-remote) — Run Grok agents on one machine, drive them from any device.
- [deepfates/haven](https://github.com/deepfates/haven) — ACP client for mobile web.

## Chat & Messaging Bridges

Talk to ACP agents from your favorite chat app.

- [formulahendry/wechat-acp](https://github.com/formulahendry/wechat-acp) — Bridge WeChat messages to any ACP agent.
- [kellyvv/WeiClaw](https://github.com/kellyvv/WeiClaw) — Turn WeChat into an entry point for any AI agent.
- [JiaqiZhang-Dev/lark-acp](https://github.com/JiaqiZhang-Dev/lark-acp) — Bridge Feishu/Lark chat to any ACP agent.
- [SuperKenVery/Telegram-ACP](https://github.com/SuperKenVery/Telegram-ACP) — Control any agent from Telegram.
- [mgaitan/telegram-acp-bot](https://github.com/mgaitan/telegram-acp-bot) — Telegram bot implementing ACP.
- [broven/acp-discord](https://github.com/broven/acp-discord) — Discord bot built on ACP.
- [nczz/kiro-discord-bot](https://github.com/nczz/kiro-discord-bot) — Trainable AI agent living in Discord, bound to your coding agent.
- [sidequery/duckdb-claude-slack](https://github.com/sidequery/duckdb-claude-slack) — Slackbot on DuckDB + Claude Code that answers data questions.
- [ominiverdi/opencode-chat-bridge](https://github.com/ominiverdi/opencode-chat-bridge) — Bridge OpenCode to Matrix, Slack, Mattermost, WhatsApp, and Discord.

## Coding Agents

AI coding agents that speak ACP and can be driven by any client. The list below mirrors the [official agents page](https://agentclientprotocol.com/overview/agents) and [CI-verified registry](https://github.com/agentclientprotocol/registry); see the [live protocol matrix](https://github.com/agentclientprotocol/registry/blob/main/.protocol-matrix/latest.md) for capability support.

| Agent | By | Link |
| --- | --- | --- |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Google | The first ACP reference agent. |
| [Claude Agent](https://github.com/agentclientprotocol/claude-agent-acp) | Anthropic/ACP | Use the Claude Agent SDK from any ACP client. |
| [Codex CLI](https://github.com/zed-industries/codex-acp) | OpenAI/Zed | ACP server exposing Codex CLI. |
| [GitHub Copilot](https://github.com/github/copilot-cli) | GitHub | Copilot CLI & language server with ACP. |
| [Cursor](https://cursor.com/docs/cli/acp) | Anysphere | Cursor CLI agent over ACP. |
| [OpenCode](https://github.com/sst/opencode) | SST | Open-source terminal agent. |
| [goose](https://github.com/block/goose) | Block | Extensible open-source agent. |
| [Qwen Code](https://github.com/QwenLM/qwen-code) | Alibaba | Qwen-powered coding agent. |
| [Kimi CLI](https://github.com/MoonshotAI/kimi-cli) | Moonshot AI | Kimi coding agent. |
| [Mistral Vibe](https://github.com/mistralai/mistral-vibe) | Mistral | Mistral's coding agent. |
| [Cline](https://github.com/cline/cline) | Cline | Popular autonomous coding agent. |
| [Kilo](https://github.com/Kilo-Org/kilocode) | Kilo | Kilocode agent. |
| [Auggie CLI](https://github.com/augmentcode/auggie) | Augment | Augment Code's CLI agent. |
| [Junie](https://github.com/JetBrains/junie) | JetBrains | JetBrains' autonomous agent. |
| [Factory Droid](https://factory.ai/) | Factory | Droid coding agent. |
| [fast-agent](https://github.com/evalstate/fast-agent) | evalstate | Build & evaluate agents (MCP + ACP). |
| [DeepAgents](https://github.com/langchain-ai/deepagentsjs) | LangChain | LangChain deep agents over ACP. |
| [Stakpak](https://github.com/stakpak/agent) | Stakpak | Open-source DevOps/ship-on-autopilot agent. |
| [VT Code](https://github.com/vinhnx/VTCode) | vinhnx | LLM-native open-source coding agent. |
| [Poolside](https://github.com/poolsideai/pool) | Poolside | `pool` terminal coding agent. |
| [siGit Code](https://github.com/getsigit/sigit) | siGit | Local coding agent on Onde Inference. |
| [Amp](https://github.com/tao12345666333/amp-acp) | Sourcegraph (adapter) | ACP adapter for Amp Code. |
| [Minion Code](https://github.com/femto/minion-code) | femto | Minion coding agent. |
| [crow-cli](https://github.com/crow-cli/crow-cli) | crow | Crow coding agent. |
| [Dirac](https://github.com/dirac-run/dirac) | Dirac | Dirac coding agent. |
| [Autohand Code](https://github.com/autohandai/autohand-acp) | Autohand AI | Autohand coding agent. |
| [GLM Agent](https://github.com/stefandevo/glm-acp-agent) | community | Zhipu GLM-series ACP agent. |
| [Cortex Code](https://docs.snowflake.com/en/user-guide/cortex-code/cortex-code) | Snowflake | Snowflake Cortex agent. |
| [Corust Agent](https://github.com/Corust-ai/corust-agent-release) | Corust | Corust coding agent. |
| [pi](https://github.com/badlogic/pi-mono) | badlogic | Pi coding agent (see [pi-acp](https://github.com/svkozak/pi-acp)). |
| [OpenHands](https://docs.openhands.dev/openhands/usage/run-openhands/acp) | All-Hands AI | Autonomous software agent. |
| [Docker cagent](https://github.com/docker/cagent) | Docker | Docker's container-native agent. |
| [code-assistant](https://github.com/stippi/code-assistant) | stippi | Autonomous coding assistant (ACP + MCP). |

> Also registered/listed: AgentPool, AutoDev, Blackbox AI, Bub, CodeBuddy Code, DimCode, fount, Grok Build, Kiro CLI, Nova, OpenClaw, Qoder CLI, stdio Bus, Symposium, and more — see the [registry](https://github.com/agentclientprotocol/registry) for the always-current set.

## Agent Bridges & Adapters

Wrap a non-ACP agent or model so it can be driven by any ACP client.

- [agentclientprotocol/claude-agent-acp](https://github.com/agentclientprotocol/claude-agent-acp) — Use the Claude Agent SDK from any ACP client.
- [Xuanwo/acp-claude-code](https://github.com/Xuanwo/acp-claude-code) — ACP implementation for Claude Code.
- [zed-industries/codex-acp](https://github.com/zed-industries/codex-acp) — Expose OpenAI Codex CLI over ACP.
- [cola-io/codex-acp](https://github.com/cola-io/codex-acp) — Codex-bridging ACP agent (Rust).
- [svkozak/pi-acp](https://github.com/svkozak/pi-acp) — ACP adapter for the Pi coding agent.
- [stefandevo/glm-acp-agent](https://github.com/stefandevo/glm-acp-agent) — Zhipu GLM models as an ACP agent.
- [blowmage/cursor-agent-acp-npm](https://github.com/blowmage/cursor-agent-acp-npm) — Cursor Agent ACP adapter.
- [kingsword09/droid-acp](https://github.com/kingsword09/droid-acp) — ACP adapter for Factory Droid.
- [josephschmitt/opencode-acp](https://github.com/josephschmitt/opencode-acp) — ACP adapter for OpenCode.
- [joelreymont/banjo](https://github.com/joelreymont/banjo) — Zig implementation of a Claude Code ACP adapter for Zed.
- [moabualruz/claude-code-cli-acp](https://github.com/moabualruz/claude-code-cli-acp) — Rust PTY bridge for the real Claude Code CLI.
- [beyond5959/acp-adapter](https://github.com/beyond5959/acp-adapter) — Bridge Codex, Claude Code, and Pi to ACP.
- [jorgejhms/aider-acp](https://github.com/jorgejhms/aider-acp) — ACP adapter for Aider.
- [mshirlaw/qodo-acp-adapter](https://github.com/mshirlaw/qodo-acp-adapter) — ACP adapter for Qodo Command.
- [Open-ACP/OpenACP](https://github.com/Open-ACP/OpenACP) — Self-hosted bridge for interacting with AI coding agents.
- [EvilFreelancer/acpbox](https://github.com/EvilFreelancer/acpbox) — OpenAI-compatible HTTP gateway to ACP agents.
- [Oortonaut/mcacp](https://github.com/Oortonaut/mcacp) — MCP ↔ ACP bridge.
- [namanrajpal/acp-to-agui](https://github.com/namanrajpal/acp-to-agui) — Bridge any ACP coding agent to the AG-UI protocol.

## Orchestrators & Multi-Agent Managers

Run, route, and supervise many agents at once.

- [agent-of-empires/agent-of-empires](https://github.com/agent-of-empires/agent-of-empires) — Manage multiple Claude Code / OpenCode agents from one place.
- [xintaofei/codeg](https://github.com/xintaofei/codeg) — Collaborative multi-agent AI coding workspace.
- [phil65/agentpool](https://github.com/phil65/agentpool) — Unified agent orchestration hub.
- [leapmux/leapmux](https://github.com/leapmux/leapmux) — AI coding agent multiplexer.
- [sleep2agi/agent-network](https://github.com/sleep2agi/agent-network) — Multi-agent, one-command orchestration.
- [nekocode/agent-team](https://github.com/nekocode/agent-team) — Multi-agent CLI orchestrator via ACP.
- [beyond5959/ngent](https://github.com/beyond5959/ngent) — Wrap command-line agents that speak ACP.
- [nick-pape/grackle](https://github.com/nick-pape/grackle) — Manage and orchestrate AI coding agents.
- [raphaeltm/simple-agent-manager](https://github.com/raphaeltm/simple-agent-manager) — Run multiple coding agents on your own cloud VMs.
- [purplefish-ai/factory-factory](https://github.com/purplefish-ai/factory-factory) — Workspace-based environment for running multiple agents.
- [recailai/jockey](https://github.com/recailai/jockey) — Open-source multi-agent collaboration platform.
- [agentconnect-md/agentconnect](https://github.com/agentconnect-md/agentconnect) — Self-hosted platform running multiple ACP agents for a team, each with its own runtime, model, workspace, tools and permissions, driven from chat and from Git host issues and pull requests.
- [RyanMerlin/missioncontrol](https://github.com/RyanMerlin/missioncontrol) — Kubernetes-style control plane for AI agent fleets.
- [agentrq/agentrq](https://github.com/agentrq/agentrq) — Human-in-the-loop realtime conversational task manager.
- [kdlbs/kandev](https://github.com/kdlbs/kandev) — AI Kanban & development environment orchestrating multiple agents.
- [arielarevalo/swapclaw](https://github.com/arielarevalo/swapclaw) — Container-isolated agent runtime over ACP.
- [Embedded-Focus/agent-circus](https://github.com/Embedded-Focus/agent-circus) — Run agents in sandboxed containers communicating via ACP.

## Beyond Coding — Personal, Domain & Data Agents

ACP isn't only for writing code. These projects use it for personal assistants, finance, data, knowledge, and other verticals — and demonstrate that any agent (not just coding ones) can ride the protocol.

**Personal assistants**
- [zeroclaw-labs/zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) — Fast, small, fully autonomous AI personal assistant.
- [microclaw/microclaw](https://github.com/microclaw/microclaw) — Agentic AI assistant that lives in your chats.
- [Bitterbot-AI/bitterbot-desktop](https://github.com/Bitterbot-AI/bitterbot-desktop) — Local-first AI agent with persistent memory and emotion.
- [raphaelmansuy/edgecrab](https://github.com/raphaelmansuy/edgecrab) — Super-powerful personal assistant (Nous-inspired).
- [ArdurAI/ardur-agent](https://github.com/ArdurAI/ardur-agent) — Open-source personal AI agent that lives in your terminal.

**Finance & research**
- [puemos/bullpen](https://github.com/puemos/bullpen) — Stock and portfolio research through coding agents.
- [khanhthanhdev/infi](https://github.com/khanhthanhdev/infi) — Personal AI agent for stock and portfolio analysis.

**Knowledge & memory**
- [iwe-org/iwe](https://github.com/iwe-org/iwe) — Markdown memory system for you and your AI agent.
- [bug-ops/zeph](https://github.com/bug-ops/zeph) — Memory-first AI agent that remembers *why* decisions were made.
- [geronimo-iia/llm-wiki](https://github.com/geronimo-iia/llm-wiki) — Git-backed wiki engine with an ACP/MCP surface.

**Data & analytics**
- [sidequery/duckdb-acp](https://github.com/sidequery/duckdb-acp) — Use Claude Code & other agents from inside DuckDB.
- [datalayer/agent-runtimes](https://github.com/datalayer/agent-runtimes) — Expose AI agents through multiple protocols, including ACP.

**Domain & infra**
- [stakpak/zed-stakpak-agent-server](https://github.com/stakpak/zed-stakpak-agent-server) — DevOps agent as a Zed/ACP extension.
- [hecatehq/hecate](https://github.com/hecatehq/hecate) — Local AI operations console for supervised agent work.

## Developer Tools & Utilities

Debuggers, inspectors, observability, and helpers for building on ACP.

- [maksugr/acp-devtools](https://github.com/maksugr/acp-devtools) — See exactly what your editor and agent say to each other.
- [venikman/ACP-inspector](https://github.com/venikman/ACP-inspector) — Debug and validate ACP traffic (F#).
- [tbrandenburg/acp-inspector](https://github.com/tbrandenburg/acp-inspector) — Visual inspector and debugging tool for ACP.
- [AndreKurait/acp-traces](https://github.com/AndreKurait/acp-traces) — Add OpenTelemetry tracing to any ACP agent with zero code changes.
- [williamfzc/acp-spawn](https://github.com/williamfzc/acp-spawn) — Wrap any ACP agent with structured JSONL lifecycle events.
- [rohitpaulk/are-we-acp-yet](https://github.com/rohitpaulk/are-we-acp-yet) — Conformance probe: "your ACP server has bugs."
- [puemos/lareview](https://github.com/puemos/lareview) — Code-review workbench built on ACP.
- [aklos/scryer](https://github.com/aklos/scryer) — Visual architecture modeling for AI agents.
- [pacifio/atlas](https://github.com/pacifio/atlas) — Planning surface for coding agents.
- [remorses/openplexer](https://github.com/remorses/openplexer) — Track ACP coding sessions in Notion boards.
- [mksglu/context-mode](https://github.com/mksglu/context-mode) — Context-window optimization for coding agents.

## Examples & Templates

- [markpollack/acp-java-tutorial](https://github.com/markpollack/acp-java-tutorial) — Progressive tutorial for the ACP Java SDK.
- [mcpc-tech/ai-elements-remix-template](https://github.com/mcpc-tech/ai-elements-remix-template) — Remix starter with AI elements supporting ACP agents.
- [yoshuawuyts/playground-wasm-acp](https://github.com/yoshuawuyts/playground-wasm-acp) — Connecting wasmtime to ACP.
- [imalsogreg/baml-acp](https://github.com/imalsogreg/baml-acp) — Write coding agents using ACP with BAML.
- [Rust agent/client examples](https://github.com/agentclientprotocol/rust-sdk/tree/main/src/agent-client-protocol/examples) · [Python examples](https://github.com/agentclientprotocol/python-sdk/tree/main/examples) · [TypeScript examples](https://github.com/agentclientprotocol/typescript-sdk/tree/main/src/examples) — Official SDK examples.

## Articles, Talks & Guides

- [Bring Your Own Agent to Zed — Featuring Gemini CLI](https://zed.dev/blog/bring-your-own-agent-to-zed) — The launch announcement.
- [Zed — Agent Client Protocol](https://zed.dev/acp) — Zed's ACP landing page.
- [Agent Client Protocol: The LSP for AI Coding Agents](https://blog.promptlayer.com/agent-client-protocol-the-lsp-for-ai-coding-agents/) — PromptLayer explainer.
- [Agent Client Protocol: Making Agentic Editing Portable](https://joshuaberkowitz.us/blog/github-repos-8/agent-client-protocol-making-agentic-editing-portable-907) — Deep-dive writeup.
- [jellydn/zed-101-setup](https://github.com/jellydn/zed-101-setup) — Guide to setting up Zed (Vim mode, tasks, ACP agents).
- [Authentication in ACP](https://github.com/agentclientprotocol/registry/blob/main/AUTHENTICATION.md) — How agents implement auth handshakes.

## Related Protocols

ACP sits in a growing family of agent standards. Don't confuse the "ACP"s:

- [Agent Client Protocol](https://agentclientprotocol.com) — **this list** — editor ↔ agent (Zed).
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io) — agent ↔ tools/data (Anthropic).
- [Agent2Agent (A2A)](https://a2a-protocol.org) — agent ↔ agent (Google/Linux Foundation).
- [AG-UI](https://github.com/ag-ui-protocol/ag-ui) — agent ↔ user interface.
- [Agent Communication Protocol (ACP)](https://agentcommunicationprotocol.dev) — agent ↔ agent (IBM/BeeAI). *Different protocol, same acronym.*
- [Agentic Commerce Protocol (ACP)](https://www.agenticcommerce.dev) — AI-driven checkout (OpenAI/Stripe). *Different protocol, same acronym.*

Other curated lists worth a look: [nMaroulis/awesome-agent-client-protocol](https://github.com/nMaroulis/awesome-agent-client-protocol), [insodimension/awesome-agent-protocols](https://github.com/insodimension/awesome-agent-protocols).

## Contributing

Contributions are very welcome! This list is reproducible — the [`scripts/`](./scripts) directory harvests the ecosystem straight from the GitHub API by the `agent-client-protocol` and `acp` topics plus full-text and code search. See [CONTRIBUTING.md](./CONTRIBUTING.md) to add a project or regenerate the data.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
