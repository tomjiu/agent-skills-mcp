# Shared AI Skills + MCP

```text
E:\Code\skills\
  selected\     # ENABLED skills only (Agent discovers these)
  mcp\          # ENABLED MCP registry (enabled.yaml + local MCP repos)
  catalog\      # Indexes, policies, MCP drafts (not auto-loaded into context)
  sources\      # Pre-cloned packs & mirrors (on-demand, not default-enabled)
  archive\      # Backups / disabled / old junk
  README.md
```

| Path | Role |
|------|------|
| **`selected/`** | **只放启用的 skills**（每个子目录一个 skill） |
| **`mcp/`** | **只放启用的 MCP**：`mcp/servers/<name>/` 一目了然；`local/` 放本机源码 |
| **`catalog/`** | URL 索引、镜像列表、draft 配置、审计 |
| **`sources/`** | 预制下载（skills 大包、MCP 源码镜像、awesome）— **不默认启用** |
| **`archive/`** | 冷备份 |

## Client wiring

| Tool | Skills | MCP runtime |
|------|--------|-------------|
| **OpenCode** | `skills.paths` → `selected/` | `~/.config/opencode/opencode.json` — keep in sync with `mcp/enabled.yaml` |
| **Codex** | copy into `~/.codex/skills` | `~/.codex/config.toml` `[mcp_servers]` — keep in sync with `mcp/enabled.yaml` |
| **Hermes** | own tree | own `config.yaml` |

## Enable / disable

| Want | Skills | MCP |
|------|--------|-----|
| Enable | put under `selected/` (+ copy to Codex) | add to `mcp/enabled.yaml` **and** client config |
| Prefetch only | clone under `sources/` | clone under `sources/mcp-ecosystem/` + draft in `catalog/mcp.draft.toml` |
| Disable | move to `archive/` | remove from client config + mark in `enabled.yaml` |

## Key docs

- Enabled MCP list: **`mcp/enabled.yaml`**
- Enabled skills folder: **`selected/README.md`**
- URL catalog: `catalog/sources.yaml`
- Local clones: `catalog/LOCAL_MIRRORS.md`
- MCP not enabled yet: `catalog/mcp.draft.toml`

## Search (enabled)

- Keenable MCP · Tavily Hikari MCP · Exa (`EXA_API_KEY`)
- Skills: `web-search-hikari`, `keenable-cli`, `exa-search`, …

## Index skills

- `source-index` — local map
- `repository-skills` — remote search → download → **review** → promote to `selected/`
