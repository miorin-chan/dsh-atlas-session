# 会话模块化改良计划

[English](README.md)

继续对话、收尾或等待回复时，可以分别开启这四项功能。

- [下一步提示](../dsh-next-actions/README.zh.md)。
  点回复下方的建议，把它填入输入框继续编辑。
- [结语笔记](../dsh-session-caesura/README.zh.md)。
  一轮结束后，点发送按钮旁的 `𝄽`，把草稿存为当前浏览器里的私人笔记。
- [Agent 模式切换](../dsh-preset-switch/README.zh.md)。
  会话空闲时，从标题栏的 preset 名旁打开选择器。
- [会话声音提醒](../dsh-session-sounds/README.zh.md)。
  在 macOS 桌面端，回复完成或会话等你响应时播放提示音。

## 安装

需要 DeepSeek Harness `0.2.2-rc.5` 的 Web 客户端。

1. 在本目录运行 `pnpm install`。
2. 如果当前 profile 已单独安装其中的插件，先记下开关状态，再移除独立安装的包，避免插件 ID 重复。
3. 在 **插件 → 添加插件** 选择本目录，再到新卡片恢复已记下的开关状态。

[维护与验证](docs/README.md)
