# AGENTS.local

本包是薄聚合 bundle。`aggregate.yml` 记录成员和顺序，`cordis.patch.yml` 和 `package.json` 的聚合字段由工具生成。
保持源插件行 ID 和配置，行为改动留在源插件中。
更新成员后运行 `pnpm run aggregate` 和 `pnpm run check`，再用一次性 profile 验证启停。
交付前从工作区执行 `node tools/new-dsh-plugin/cli.mjs --check plugins/dsh-session-atlas`。

[README.md](README.md) 和 [README.zh.md](README.zh.md) 记录用户安装与使用，[项目文档](docs/README.md) 记录验证和维护。
卡片元数据同时维护八个 locale。Markdown 用 `docs/scripts/reflow md` 重排，Git 钩子用 `prek install` 安装。
