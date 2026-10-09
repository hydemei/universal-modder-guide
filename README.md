# Universal Modder tutorial

> A step-by-step, unofficial tutorial for **[universal-modder](https://github.com/rehan-remade/universal-modder)**, the open-source toolkit that lets AI coding agents (Claude Code, Codex, Cursor, Gemini CLI, Copilot, OpenCode) mod PC games you own.
>
> Full, always-current version with the game library and changelog: **https://universal-modder.dev**

This repo contains no code from universal-modder. Install the toolkit only from the official repository.

## Contents
1. [What it is](#1-what-it-is)
2. [Requirements](#2-requirements)
3. [Install by agent](#3-install-by-agent)
4. [Set up fal](#4-set-up-fal)
5. [Your first mod](#5-your-first-mod)
6. [Costs](#6-costs)
7. [Safety rules](#7-safety-rules)
8. [Troubleshooting](#8-troubleshooting)

## 1. What it is
Universal Modder gives your agent:
- **11 Agent Skills**, led by `mod-any-game`, which runs the same loop every time: search the knowledge base → recon → safe lab → read the real code → one working slice → assets → verify in game → record → package → field note.
- **The `um` CLI**: `scan`, `fal`, `comfy`, `sprite`, `render3d`, `win`, `video`, `backup`, `publish check`, `kb`.
- **A fal MCP server** for sprites, textures, 3D, SFX, music and voice.
- **A knowledge base** of field notes on how specific games were modded.

## 2. Requirements
| Need | Notes |
|---|---|
| AI coding agent | Claude Code needs a Pro/Max/Team/Enterprise plan or API billing |
| Git, Python 3.10+, ffmpeg | required |
| uv | recommended for the CLI |
| fal API key | only for generated assets |
| Blender | only for 3D → sprite renders |

Windows: `winget install Git.Git Python.Python.3.12 astral-sh.uv Gyan.FFmpeg`
macOS: `brew install git python ffmpeg uv`

## 3. Install by agent
| Agent | Install |
|---|---|
| Claude Code | `/plugin marketplace add rehan-remade/universal-modder` then `/plugin install universal-modder@universal-modder` |
| Codex | `codex plugin marketplace add rehan-remade/universal-modder` then `codex plugin add universal-modder@universal-modder` |
| Gemini CLI | `gemini extensions install https://github.com/rehan-remade/universal-modder` |
| VS Code / Copilot | enable `chat.plugins.enabled`, run **Chat: Install Plugin From Source**, paste the repo URL |
| Cursor | Cursor Marketplace, or clone the repo |
| OpenCode | clone and run `opencode` inside it |
| Any agent | `npx skills add https://github.com/rehan-remade/universal-modder` |

CLI only: `uv tool install git+https://github.com/rehan-remade/universal-modder`

Detailed walkthrough: https://universal-modder.dev/install/ · Claude Code deep-dive: https://universal-modder.dev/claude-code/

## 4. Set up fal
Create a key at https://fal.ai/dashboard/keys, then:
```bash
export FAL_KEY="your-key"   # macOS / Linux / WSL
setx FAL_KEY "your-key"     # Windows (open a new terminal after)
```
No key? `um comfy` makes images with a local ComfyUI server.

## 5. Your first mod
```text
What engine is my copy of Terraria, has anyone modded it before, and what route would you take? Don't change anything yet.
```
Then:
```text
Add one boomerang that bounces between enemies four times before returning. Placeholder sprite first, then a fal sprite once it works in game.
```
Good first games: Terraria (tModLoader), Stardew Valley (SMAPI), Minecraft (Fabric), Unity games with BepInEx. Game library: https://universal-modder.dev/games/

## 6. Costs
Toolkit: free (MIT). fal, checked October 2026: ~$0.211 per high-quality sprite, $0.08 per image, $0.25–0.35 per 3D model, $0.002 per second of SFX. A small content pack is about $2.51. Calculator: https://universal-modder.dev/cost/

## 7. Safety rules
- Games you own: single-player, offline, or servers you host.
- No anti-cheat bypass, no cheats against other players, no DRM tampering.
- Saves backed up first; the agent asks before driving input, installing loaders or publishing.
- Never ship game files or decompiled code.

More: https://universal-modder.dev/safety/

## 8. Troubleshooting
- **SSH error adding the marketplace:** `git config --global url."https://github.com/".insteadOf git@github.com:`
- **Skills missing:** `/reload-plugins` or restart the agent.
- **`um` not found:** open a new terminal or `uv tool update-shell`.
- **fal key missing:** restart the agent after setting `FAL_KEY`.

---
Unofficial, community-maintained. Not affiliated with the universal-modder maintainers. Text licensed CC BY 4.0.
