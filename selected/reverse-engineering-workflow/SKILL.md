---
name: reverse-engineering-workflow
description: Use for reverse engineering, malware analysis, Android APK static analysis, or tool selection (Ghidra, Frida, JADX, radare2). Index-first; load domain packs on demand. Authorized analysis only.
---

# Reverse Engineering Workflow

## Why this skill exists

Large “awesome” lists and official orgs often **omit** niche RE skills. Community packs fill gaps but quality varies. Always:

1. `source-index` → canonical tool URL
2. Use official tools (Ghidra/Frida/JADX) via terminal
3. Load community skill packs only when they match the platform

## Local on-demand packs

| Pack | Path | Notes |
|------|------|-------|
| P4nda0s reverse-skills | `E:\Code\skills\sources\packs\reverse-skills-p4nda0s\skills\` | Frida, IDA, Unicorn, Unity, dex dump… |
| Android RE (Codex) | `E:\Code\skills\sources\packs\android-re-skill-codex\` | APK/JADX oriented |
| Ghidra MCP (bethington) | `E:\Code\skills\sources\mcp-ecosystem\ghidra-mcp-bethington` | precloned; enable MCP only after Ghidra ready |
| Ghidra headless MCP | `E:\Code\skills\sources\mcp-ecosystem\ghidra-headless-mcp` | precloned; agent-friendly headless |
| Frida MCP (dnakov) | `E:\\Code\\skills\\sources\\mcp-ecosystem\\frida-mcp-dnakov` | precloned; needs Frida |
| Frida MCP Kahlo | `E:\\Code\\skills\\sources\\mcp-ecosystem\\frida-mcp-kahlo` | Android-oriented |
| Catalog | `E:\Code\skills\catalog\sources.yaml` → `reverse_engineering`, `android`, `firmware`, `dfir` | URLs only |

## Standard flow

1. Identify target type (PE/ELF/APK/firmware/memory)
2. Pick tool from catalog (official first)
3. Static: strings, imports, decompile (Ghidra/JADX/r2)
4. Dynamic (if authorized): Frida/Objection
5. Notes + artifacts under project dir; no unsolicited C2/exploit

## Do not auto-load

- Claude-Red / full offensive packs unless user explicitly requests **and** authorization is clear
- Do not run decoder/python -c on chat stickers (unrelated)

## Output

State: target type, tools chosen (with URLs from catalog), next commands.
