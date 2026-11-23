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
  在侧栏打开会话行的 `⋯` 菜单，选择 **标题历史**，查看标题何时生成或修改。

## 兼容条件

需要 DeepSeek Harness `0.2.2-rc.5` 的 Web 客户端。

## 安装

1. 在聚合包目录运行 `pnpm install`。
2. 如果目标 profile 已单独安装任何成员，记下开关状态，再移除独立安装的包，避免行 ID 重复。
3. 在 **插件 → 添加插件** 选择聚合包目录，然后在新卡片恢复各成员的开关状态。

[聚合清单](../aggregate.yml)声明源插件的顺序和版本范围。
生成器复制源插件的行 ID 与初始配置。
卡片的启停由 profile 的 bundle 选择管理，卡内开关按行 ID 管理。

## 维护

在本目录运行 `pnpm run aggregate` 更新产物，再运行 `pnpm run check`。
成员有变动时重新运行 `pnpm install`。
本包通过工作区相邻目录的 `link:` 依赖安装。

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
  when titles were generated or edited.

## Compatibility

Requires the Web client on DeepSeek Harness `0.2.2-rc.5`.

## Install

1. Run `pnpm install` from the bundle directory.
2. If any member is installed separately in the target profile, note its switch state and remove its bundle
   to avoid duplicate row IDs.
3. In **Plugins → Add plugin**, select the bundle directory.
   Restore the saved switch states on the new card.
