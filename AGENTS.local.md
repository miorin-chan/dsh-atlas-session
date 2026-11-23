# AGENTS.local

本包是薄聚合 bundle。`aggregate.yml` 记录成员和顺序，`cordis.patch.yml` 和 `package.json` 的聚合字段由工具生成。
保持源插件行 ID 和配置，行为改动留在源插件中。
在源插件中编写源码时，除非有特殊说明，否则使用 TypeScript。
更新成员后按[维护说明](docs/README.md#维护)安装固定版本、构建并检查，再用一次性 profile 验证启停。
交付前从工作区执行 `node tools/new-dsh-plugin/cli.mts --check plugins/dsh-atlas-session`。

[README.md](README.md) 和 [README.zh.md](README.zh.md) 记录用户安装与使用，[项目文档](docs/README.md) 记录验证和维护。
卡片元数据同时维护八个 locale。Markdown 用 `docs/scripts/reflow md` 重排，Git 钩子用 `prek install` 安装。
插件详情页要整体短、每项一眼能懂。
只展示用户当下需要知道或操作的内容，细节按需展开。

## 复用 DSH 原生界面

- 优先复用 DSH 原生组件、行为、主题 token 和同类界面布局，以减少自写代码和维护成本。
- 当前版本有受支持的运行时入口且性能可接受时，优先通过公开插槽、
  组件工厂或宿主提供的可加载模块动态复用，让宿主提供组件实现。
  只有现有组件和扩展点无法满足需求时，才补足必要的插件实现。
- 静态引入或打包官方代码或资源时，在引用处标注上游包名、版本或提交、源码路径及符号名，便于升级时回看和同步，
  并保留适用的许可证与署名。
