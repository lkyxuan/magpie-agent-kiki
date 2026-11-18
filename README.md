# Kiki (getkiki.ai) × Magpie

把 [Kiki](https://getkiki.ai)（Mac 上的 AI 首席秘书，带一支 AI 团队）接进 [Magpie](https://github.com/yetone/magpie) 的 Agent 页：在 Magpie 里给 Kiki 选一个模型，Kiki 和所有团队成员就都走 Magpie 的本地网关。Magpie 里能用的模型（各家 API key、Claude / ChatGPT / Copilot 等订阅、本地模型）Kiki 都能用；同一个订阅登了几个账号，额度用完会自动换下一个。

Adds [Kiki](https://getkiki.ai), the Mac app where one chief of staff runs a team of AI agents, to Magpie's Agents page. Pick a model on Kiki's row and Kiki (and every team member in it) goes through Magpie's local gateway, with every provider, subscription and account failover Magpie has.

## 安装 / Install

> 跟 [X-T-E-R/kiki](https://github.com/X-T-E-R/kiki) 的 `magpie-agent-kiki` 不是同一个产品：那个是开源的多模型工作台，配置在 `~/.kiki`；这个是 getkiki.ai 的 Mac App，数据在 `~/kiki-data`。所以这里的 id 叫 `getkiki`。
> Not the same product as X-T-E-R/kiki's `magpie-agent-kiki` (an open-source workbench, config in `~/.kiki`). This is the getkiki.ai Mac app (data in `~/kiki-data`), so its id is `getkiki`.

```sh
magpie plugin add @magpie-community/agent-getkiki
```

或者在 Magpie 里打开 插件 → 发现，搜 Kiki。

还没发到 npm 时，可以直接用这个仓库：

```sh
git clone https://github.com/lkyxuan/magpie-agent-kiki
magpie plugin add ./magpie-agent-kiki
```

## 它改什么 / What it writes

| 文件 | 写什么 |
| --- | --- |
| `~/kiki-data/engine/models.json` | 一个叫 `magpie` 的供应商：网关地址、Magpie 给 Kiki 的 key、Magpie 给 Kiki 的全部模型 |
| `~/kiki-data/.env` | `MODEL=magpie/<供应商>/<模型>`，Kiki 默认用的模型 |

在 Magpie 里关掉 Kiki 那一行，或者选回 Kiki 原来的模型，两个文件都恢复原样。Kiki 的其他供应商、密钥和设置不动。

Kiki 启动时读模型，换完要 ⌘Q 退出 Kiki 再打开。之后 Kiki 自己的模型菜单里也能直接选 Magpie 的模型。

Kiki 的数据目录不是 `~/kiki-data`（设了 `DATA_DIR`）时，这个插件目前找不到它。

## 测试 / Test

```sh
node --test kiki.test.mjs
```

## 许可 / License

MIT。写法参考了 [magpie-community/plugins](https://github.com/magpie-community/plugins) 的 PiG 插件（MIT）。
