# Changelog

## 2026-07-17

- Added a dedicated `ChatGPT` strategy group and `rules/chatgpt.yaml`.
- Moved ChatGPT/OpenAI domains out of the generic AI rules.
- Added inline ChatGPT/OpenAI routing rules before all rule providers so Stash still proxies ChatGPT when its iCloud ruleset cache fails.
- Changed `Singapore-AI` from automatic latency testing to manual selection to keep a stable exit IP and avoid silent switching to an incorrectly labeled Hong Kong exit.
- Kept Japan and Taiwan as explicit ChatGPT fallback groups while preserving Singapore as the primary policy.
- Diagnosed Stash `resource deadlock avoided` errors as an iCloud resource-cache failure that can leave proxy groups empty and fall back to direct access.

## 2026-07-09

- Added `Tyler.remote.yaml` for Stash and URL-based imports, using GitHub Raw rule providers.
- Documented separate import paths for Clash Verge Rev, Stash, and Mihomo/LuCI.
- Kept the remote profile subscription field as a placeholder so real airport tokens stay out of Git.
- Updated platform target from FlClash to Clash Verge Rev on Mac while keeping Stash and Mihomo/LuCI compatibility.
- Confirmed Mudi 7 uses regular Mihomo/LuCI style deployment, so the profile remains a General Config style portable YAML.
- Added dedicated Claude strategy group and `rules/claude.yaml` for Claude/Anthropic traffic.
- Split Claude/Anthropic domains out of generic AI rules so Claude can use more stable non-mainland nodes.
- Converted `Tyler_20260709.conf` from Shadowrocket-style rules into a Mihomo/Clash YAML profile.
- Added `Tyler.yaml` as the unified profile for FlClash, Stash, and Mihomo.
- Added split rule providers for AI, Gemini, YouTube, Google, Apple, China, and compatible legacy rules.
- Routed non-Gemini AI traffic to `Singapore-AI`.
- Routed Gemini traffic through Japan/Taiwan strategy group `Gemini`.
- Routed YouTube traffic to `Singapore-Media`.
- Routed Apple, China mainland, and private networks to `DIRECT`.
- Kept subscription tokens and real nodes out of `Tyler.yaml` by using ignored local file provider `./private/proxies.yaml`.
- Split compatible legacy rules by action into reject, proxy, and direct rule providers.
- Recorded non-portable Shadowrocket rules in `rules/unsupported-shadowrocket-rules.md`.
