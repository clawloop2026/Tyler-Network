# Tyler Network

Personal network routing profile for Clash Verge Rev on Mac, Stash on iPhone, and Mihomo/LuCI on Mudi 7.

## Configuration approach

This repository follows the General Config style recommended for regular Clash Meta/Mihomo clients. The Mudi 7 screenshot shows `mihomo` and `luci-app-mihomo`, not a Smart kernel, so this profile stays on portable Mihomo/Clash YAML instead of Smart Mode or OpenClash-only overwrite files.

## Files

- `Tyler.yaml` is the single main profile to import.
- `rules/ai.yaml` routes non-Gemini and non-Claude AI traffic to `Singapore-AI`.
- `rules/claude.yaml` routes Claude traffic to the dedicated `Claude` strategy group.
- `rules/gemini.yaml` routes Gemini traffic to `Gemini`, which selects Japan/Taiwan nodes.
- `rules/youtube.yaml` routes YouTube traffic to `Singapore-Media`.
- `rules/apple.yaml` and `rules/china.yaml` route Apple, China mainland, and private networks directly.
- `rules/legacy-reject.yaml`, `rules/legacy-proxy.yaml`, and `rules/legacy-direct.yaml` contain compatible legacy rules converted from the old Shadowrocket profile.
- `rules/unsupported-shadowrocket-rules.md` records old rules that were not migrated because they are not portable across the target clients.

## Private proxies

`Tyler.yaml` uses a local file provider at `./private/proxies.yaml`. This file is intentionally ignored by Git.

Create it from `private/proxies.example.yaml`, then fill the local copy only. Do not put airport subscription URLs or tokens in `Tyler.yaml`.

## Routing policy

- AI except Gemini and Claude: `Singapore-AI`
- Claude: dedicated `Claude` strategy group, preferring stable non-mainland nodes
- Gemini: `Japan` / `Taiwan` through `Gemini`
- YouTube: `Singapore-Media`
- Apple and China mainland: `DIRECT`
- Fallback: `Proxy`
