# 项目文档

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
