# Tyler Network

Personal network routing profile for Clash Verge Rev on Mac, Stash on iPhone, and Mihomo/LuCI on Mudi 7.

## Configuration approach

This repository follows the General Config style recommended for regular Clash Meta/Mihomo clients. The Mudi 7 screenshot shows `mihomo` and `luci-app-mihomo`, not a Smart kernel, so this profile stays on portable Mihomo/Clash YAML instead of Smart Mode or OpenClash-only overwrite files.

## Files

- `Tyler.yaml` is the local main profile for Clash Verge Rev on Mac and Mihomo/LuCI on Mudi 7.
- `Tyler.remote.yaml` is the remote main profile for Stash on iPhone or any client that imports by URL.
- `rules/chatgpt.yaml` routes ChatGPT/OpenAI traffic to the dedicated `ChatGPT` strategy group.
- `rules/ai.yaml` routes other non-Gemini and non-Claude AI traffic to `Singapore-AI`.
- `rules/claude.yaml` routes Claude traffic to the dedicated `Claude` strategy group.
- `rules/gemini.yaml` routes Gemini traffic to `Gemini`, which selects Japan/Taiwan nodes.
- `rules/youtube.yaml` routes YouTube traffic to `Singapore-Media`.
- `rules/apple.yaml` and `rules/china.yaml` route Apple, China mainland, and private networks directly.
- `rules/legacy-reject.yaml`, `rules/legacy-proxy.yaml`, and `rules/legacy-direct.yaml` contain compatible legacy rules converted from the old Shadowrocket profile.
- `rules/unsupported-shadowrocket-rules.md` records old rules that were not migrated because they are not portable across the target clients.

## Private proxies

`Tyler.yaml` uses a local file provider at `./private/proxies.yaml`. This file is intentionally ignored by Git.

Create it from `private/proxies.example.yaml`, then fill the local copy only. Do not put airport subscription URLs or tokens in `Tyler.yaml`.

`Tyler.remote.yaml` uses an HTTP proxy-provider placeholder:

```yaml
url: https://example.invalid/replace-with-your-private-subscription-url
```

Replace that placeholder only inside your client or a private local copy. Do not commit the real subscription URL.

## Import guide

### Mac: Clash Verge Rev

Use the local profile:

```text
/Users/tyler/Documents/Tyler-Network Github/Tyler.mac.local.yaml
```

Clash Verge Rev restricts file providers to its application support directory. The local profile points to the synchronized `Tyler-Network` folder under that allowed directory.

### iPhone: Stash

Use the remote profile:

```text
https://raw.githubusercontent.com/clawloop2026/Tyler-Network/main/Tyler.remote.yaml
```

Important: GitHub Raw URLs are easiest when this repository is public. If the repository stays private, Stash may not be able to fetch the remote profile and rule providers without an authenticated URL. In that case, import a private local copy or make only the rules/config repository public while keeping real nodes out of GitHub.

If the Stash log contains `resource deadlock avoided`, turn off Stash iCloud synchronization, clear its downloaded resources, and re-import the profile. This error prevents rule and proxy providers from being stored and can make policy groups fall back to direct access.

When the iPhone is connected to the Mudi 7 Wi-Fi, use Mudi's Mihomo as the only active proxy layer and turn Stash off. Use Stash on cellular data or ordinary Wi-Fi. Running both layers at the same time can cause double proxying and inconsistent exit locations.

### Mudi 7: Mihomo/LuCI

Use the local profile and copy the whole folder to the device, for example:

```text
/etc/mihomo/Tyler-Network/Tyler.yaml
```

Keep this structure on the device:

```text
Tyler.yaml
rules/
private/proxies.yaml
```

## Routing policy

- ChatGPT/OpenAI: dedicated `ChatGPT` group; manually pin one verified non-Hong-Kong node
- AI except ChatGPT, Gemini, and Claude: `Singapore-AI`
- Claude: dedicated `Claude` strategy group, preferring stable non-mainland nodes
- Gemini: `Japan` / `Taiwan` through `Gemini`
- YouTube: `Singapore-Media`
- Apple and China mainland: `DIRECT`
- Fallback: `Proxy`
