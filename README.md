# Universal Modder Install Guide (Claude Code, Codex & more)

> How to install and use **[universal-modder](https://github.com/rehan-remade/universal-modder)**, the open-source toolkit that lets AI coding agents mod PC games you own.
>
> 📘 Full guide with the game library, costs and changelog: **[universal-modder.dev](https://universal-modder.dev/)** · Quick reference: **[Google Sites guide](https://sites.google.com/view/universal-modder)**

This is an unofficial, community guide. It contains no code from universal-modder, so install the toolkit only from the official repository.

| | |
|---|---|
| Official repo | [rehan-remade/universal-modder](https://github.com/rehan-remade/universal-modder) |
| Maintainer | rehan-remade |
| Stars / forks | 5.7k+ / 540+ (October 2026) |
| License | MIT, free |
| Agents | 7 install routes (table below) |

## Contents
- [What it is](#what-it-is)
- [Requirements](#requirements)
- [Three ways to install](#three-ways-to-install)
- [Install by agent (7 routes)](#install-by-agent-7-routes)
- [Set up fal](#set-up-fal)
- [Your first mod](#your-first-mod)
- [Common errors](#common-errors)
- [FAQ](#faq)

## What it is
Universal Modder gives your agent:
- **11 Agent Skills**, led by `mod-any-game`. It runs the same 10-step loop every time: search the knowledge base, recon, set up a safe lab, read the real code, build one working slice, generate assets, verify in game, record, package, write a field note. 12 engine playbooks back it up (Unity, Unreal, .NET/XNA, Godot, Source, Bethesda, Minecraft, AoE2, RE Engine/FromSoft/GTA, native C++, indie engines, retro decomps).
- **The `um` CLI**: `scan`, `fal`, `comfy`, `sprite`, `render3d`, `win`, `video`, `backup`, `publish check`, `kb`.
- **A fal MCP server** for sprites, textures, 3D, SFX, music and voice.
- **A knowledge base** of field notes on how specific games were modded.

## Requirements
| Need | Notes |
|---|---|
| AI coding agent | Claude Code needs a Pro/Max/Team/Enterprise plan or API billing |
| Git, Python 3.10+, ffmpeg | required |
| uv | recommended for the CLI |
| fal API key | only for generated assets |
| Blender | only for 3D → sprite renders |

Windows: `winget install Git.Git Python.Python.3.12 astral-sh.uv Gyan.FFmpeg`
macOS: `brew install git python ffmpeg uv`

## Three ways to install

**1. Plugin** (Claude Code shown; other agents in the next table)
```text
/plugin marketplace add rehan-remade/universal-modder
/plugin install universal-modder@universal-modder
```

**2. Clone** and start your agent inside the folder
```bash
git clone https://github.com/rehan-remade/universal-modder
```

**3. CLI only.** `um` is installed from GitHub; it is **not on PyPI**, so `pip install universal-modder` won't work.
```bash
uv tool install git+https://github.com/rehan-remade/universal-modder
# or
pipx install git+https://github.com/rehan-remade/universal-modder
```

## Install by agent (7 routes)
| Agent | Install |
|---|---|
| Claude Code | `/plugin marketplace add rehan-remade/universal-modder` then `/plugin install universal-modder@universal-modder` |
| Codex | `codex plugin marketplace add rehan-remade/universal-modder` then `codex plugin add universal-modder@universal-modder` |
| Gemini CLI | `gemini extensions install https://github.com/rehan-remade/universal-modder` |
| VS Code / Copilot | enable `chat.plugins.enabled`, run **Chat: Install Plugin From Source**, paste the repo URL |
| Cursor | Cursor Marketplace, or clone the repo |
| OpenCode | clone and run `opencode` inside it |
| Any Agent Skills agent | `npx skills add https://github.com/rehan-remade/universal-modder` |

Detailed walkthrough: [universal-modder.dev/install](https://universal-modder.dev/install/) · Claude Code deep-dive: [universal-modder.dev/claude-code](https://universal-modder.dev/claude-code/)

## Set up fal
Create a key at https://fal.ai/dashboard/keys, then:
```bash
export FAL_KEY="your-key"   # macOS / Linux / WSL
setx FAL_KEY "your-key"     # Windows (open a new terminal after)
```
No key? `um comfy` makes images with a local ComfyUI server. Prices (checked October 2026): ~$0.211 per high-quality sprite, $0.08 per image, $0.25–0.35 per 3D model, $0.002 per second of SFX. [Cost calculator](https://universal-modder.dev/cost/).

## Your first mod
```text
What engine is my copy of Terraria, has anyone modded it before, and what route would you take? Don't change anything yet.
```
```text
Add one boomerang that bounces between enemies four times before returning. Placeholder sprite first, then a fal sprite once it works in game.
```
Good first games: Terraria (tModLoader), Stardew Valley (SMAPI), Minecraft (Fabric), Unity games with BepInEx. [Game library](https://universal-modder.dev/games/).

## Common errors
| Error | Fix |
|---|---|
| Git/SSH error adding the marketplace | `git config --global url."https://github.com/".insteadOf git@github.com:` |
| Skills don't appear | `/reload-plugins` or restart the agent |
| `um: command not found` | open a new terminal, or `uv tool update-shell` |
| `pip install universal-modder` fails | it's not on PyPI; use the `git+https://` form above |
| fal key missing | set `FAL_KEY`, then restart the agent |
| `um win` refuses to run | game control is Windows / WSL only |

## FAQ
**Is Universal Modder free?** Yes, it's MIT licensed. Your agent plan and fal assets are billed separately.

**Does it work on Mac or Linux?** Install, knowledge base, asset tools and backups do. Driving and recording the game (`um win`) is Windows or WSL only.

**Will I get banned?** Not if you keep to games you own, offline or on servers you host. It refuses anti-cheat bypasses and cheats against other players. [Safety rules](https://universal-modder.dev/safety/).

**Is it the same as universal-game-modder?** No. That's an unrelated npm MCP server. [Comparison](https://universal-modder.dev/vs/universal-game-modder/).

**Can it mod Minecraft / GTA 5 / Palworld?** Minecraft and GTA V have working field notes; Palworld has none yet. See [Minecraft](https://universal-modder.dev/games/minecraft/), [GTA 5](https://universal-modder.dev/games/gta-v/) and [Palworld](https://universal-modder.dev/games/palworld/).

---
Unofficial and community-maintained; not affiliated with the universal-modder maintainers. Guide text CC BY 4.0. Main site: **[universal-modder.dev](https://universal-modder.dev/)** · Google Sites: **[sites.google.com/view/universal-modder](https://sites.google.com/view/universal-modder)**
