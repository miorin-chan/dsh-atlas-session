# 项目文档

## 使用

- [下一步提示](../../dsh-next-actions/README.zh.md)。
  点回复下方的建议，把它填入输入框继续编辑。
- [结语笔记](../../dsh-session-caesura/README.zh.md)。
  一轮结束后，点发送按钮旁的 `𝄽`，把草稿存为当前浏览器里的私人笔记。
- [Agent 模式切换](../../dsh-preset-switch/README.zh.md)。
  会话空闲时，从标题栏的 preset 名旁打开选择器。
- [会话声音提醒](../../dsh-session-sounds/README.zh.md)。
  在 macOS 桌面端，回复完成或会话等你响应时播放提示音。
- [会话标题历史](../../dsh-session-title-history/README.zh.md)。
  在侧栏打开会话行的 `⋯` 菜单，选择 **标题历史**，查看标题何时生成或修改；点过去标题右侧的 `↗` 可把它设回当前标题，
  对话里的 Agent 也能用 `session_title_history` 工具设回。

- [君子未言](../../dsh-session-rewind/README.zh.md)。
  在普通用户消息的复制按钮左侧点回退图标，可将该轮消息放回输入框并归档原对话。

- [消息翻译](../../dsh-message-translate/README.zh.md)。
  在用户消息或助手回复的操作行点翻译图标，把该条消息发给 Google 翻译并在下方显示译文。

- [排队发送提示](../../dsh-composer-queue-indicator/README.zh.md)。
  会话忙碌时，若 Enter 会将草稿加入队列，按钮就显示排队图标。
  按住 Cmd 或 Ctrl 时预览 Mod+Enter 的互补动作，点击和快捷键行为不变。

## 兼容条件

需要 DeepSeek Harness `0.2.2-rc.5` 的 Web 客户端。

## 安装

1. 在同一工作区的「君子未言」「消息翻译」和「排队发送提示」目录分别运行 `npm ci`（或 `npm install`），
   再到聚合包目录运行 `pnpm install`。
2. 如果目标 profile 已单独安装任何成员，记下开关状态，再移除独立安装的包，避免行 ID 重复。
3. 在 **插件 → 添加插件** 选择聚合包目录，然后在新卡片恢复各成员的开关状态。

[聚合清单](../aggregate.yml)声明源插件的顺序和来源。
「君子未言」「消息翻译」和「排队发送提示」使用指向同工作区源码的本地 `link:`。
生成器复制源插件的行 ID 与初始配置。
卡片的启停由 profile 的 bundle 选择管理，卡内开关按行 ID 管理。

## 维护

在 Node.js 22.18 或更新版本运行 `pnpm install`，
安装固定版本并从 `scripts/aggregate/` 的 TypeScript 源码构建 `scripts/dsh-aggregate.mjs`，再更新入库的 patch。
`npm test` 重新生成并校验，`npm run check` 只读检查生成器和聚合字段是否有漂移。
手动生成用 `npm run build`，原有的 `pnpm run aggregate` 仍可用。
新增或升级成员时，先更新[聚合清单](../aggregate.yml)。
对注册表成员，用 `pnpm add --save-exact --ignore-scripts <包名>@<版本>` 装齐新版本。
对 `link:` 成员，先构建该成员的本地源码。
再执行 `npm run build` 与 `pnpm install`，同步提交依赖清单、锁文件和 patch。

联调本地成员时，先在各成员的检出目录构建，再用聚合包 `node_modules` 里的本地链接，成员版本须匹配固定版本。
`npm pack --dry-run --json` 会重新生成 patch 并列出包内文件，可使用版本匹配的本地链接。
发布从独立干净检出执行 `pnpm install --frozen-lockfile`，检查生成的改动并运行 `npm test`。
发布检查要求成员来自该检出的注册表依赖树。
发布前需将「君子未言」「消息翻译」和「排队发送提示」改为可从 npm 安装的固定版本。
发布包中的 `scripts/dsh-aggregate.mjs` 包含 YAML 解析器。
装好成员依赖后，可用 `node scripts/dsh-aggregate.mjs check .` 校验。

在一次性 Web profile 中核对整卡、逐行启停和各功能的独立使用。
迁移现有 profile 时，先记下各成员的开关状态，移除独立 bundle，再安装聚合卡并核对各行。
如果要改回独立安装，先移除聚合卡。

## 验证记录

2026-11-21 在 DSH `0.2.2-rc.5` 上与 Mobile Atlas 同装至一次性 Web profile，隔离服务器成功监听回环端口。
合成配置中的三个成员行各出现一次，行 ID 和初始配置与源插件一致。
通过 `--patch` 逐行覆盖停用和启用状态，并用一次性 profile 的 CLI 移除及恢复整包。
每次操作后核对其他成员行。骨架检查、清单漂移检查和打包内容检查均通过。

`--dump-config-schema` 在没有安装聚合包的同版本 Web profile 中也会报告四处 `unrecognized Loader tree carrier`，
本次使用能成功导出的 `--dump-config` 核对加载配置。
浏览器插件页的视觉和点击结果尚未验证。
真实回复后的建议卡、结语展示和切换 preset 后的首轮仍需交互验证。

2026-11-24 在 DSH `0.2.2-rc.5` 的一次性 Web profile 中用 `--dump-config` 核对了八个成员行。
用 `--patch` 单独停用和恢复排队发送提示时，其他七行保持不变；移除和重新添加聚合包后，八行一并移除和恢复。
这项验证只覆盖配置合成，不覆盖浏览器里的图标和发送行为。

## Usage

- [Next actions](../../dsh-next-actions/README.md).
  Click a suggestion below a reply to put it in the composer for editing.
- [Closing note](../../dsh-session-caesura/README.md).
  After a turn, click `𝄽` beside Send to save the draft as a private note in this browser.
- [Agent mode switch](../../dsh-preset-switch/README.md).
  When the session is idle, open the menu beside the preset name in the header.
- [Session sounds](../../dsh-session-sounds/README.md).
  On macOS Desktop, hear a cue when a reply finishes or the session needs your response.
- [Session title history](../../dsh-session-title-history/README.md).
  In the sidebar, open the session row’s `⋯` menu and select **Title history** to see
  when titles were generated or edited; click `↗` beside a past title to make it current again,
  or let the conversation’s Agent restore one with the `session_title_history` tool.

- [Left Unsaid](../../dsh-session-rewind/README.md).
  Click the rewind icon beside **Copy** on an ordinary user message to return it to the composer
  and archive the original conversation.

- [Message translation](../../dsh-message-translate/README.md).
  Click the translate icon in a user or assistant message’s action row to send that message to Google Translate
  and show the result below.

- [Queue send indicator](../../dsh-composer-queue-indicator/README.md).
  While the session is busy, Send shows a queue icon when Enter would queue the draft.
  Hold Cmd or Ctrl to preview Mod+Enter.
  Clicking and both shortcuts work as before.

## Compatibility

Requires the Web client on DeepSeek Harness `0.2.2-rc.5`.

## Install

1. Run `npm ci` (or `npm install`) in the Left Unsaid, Message translation, and Queue send indicator checkouts
   in the same workspace, then run `pnpm install` in the bundle directory.
2. If any member is installed separately in the target profile, note its switch state and remove its bundle
   to avoid duplicate row IDs.
3. In **Plugins → Add plugin**, select the bundle directory.
   Restore the saved switch states on the new card.
