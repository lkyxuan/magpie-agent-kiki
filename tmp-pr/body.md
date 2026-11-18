<!-- claude-projects-attribution: {"github_login":"lkyxuan"} -->
_Requested by **0xmiracle** · [project thread](https://claude.ai/code/project/chan_01JmUCZXej3WbzeZPzv79RKg?thread=cmsg_01JmUCZXej3WbzeZPzv79RKgS3scj8GnAKySW7XCWhTH1A)_

Adds `@magpie-community/agent-getkiki`: [Kiki](https://getkiki.ai), a Mac app where one chief of staff runs a team of AI agents, on magpie's Agents page.

- `connect` writes one whole provider, `providers.magpie`, into `~/kiki-data/engine/models.json` (Kiki runs pi 1.5.0 on that folder): the gateway's `/v1`, magpie's key for Kiki, `openai-completions`, and every model with context, max output, image input and thinking levels.
- `startup` puts the picked model in `MODEL=` of `~/kiki-data/.env` (prefix `magpie/`), the model Kiki starts on. Kiki reads it when it starts, so the row's notice says to quit and reopen it.
- Switching it off puts both back; Kiki's other providers and settings are untouched.

**Not the same product as X-T-E-R/kiki** (npm `magpie-agent-kiki`, config in `~/.kiki`). That name and the id `kiki` are taken by it, so this one is `getkiki` and shows as "Kiki (getkiki.ai)". The README, the registry summary and the Agents table all say so.

Checks: `bun scripts/check.mjs getkiki` (registry ok), `bun test packages/getkiki/getkiki.test.mjs` (5 pass).

🤖 Generated with [Claude Code](https://claude.com/claude-code)

https://claude.ai/code/session_01JcTXmDsqi33LdhYjNQTW27
