# 会话 Atlas

[English](README.md)

把三项会话内增强装到插件页的同一张卡上，每行都可以独立开关。

- [下一步提示](../dsh-next-actions/README.zh.md)。
  点击回复下方的建议，把它填入输入框，供你编辑和发送。
- [结语笔记](../dsh-session-caesura/README.zh.md)。
  一轮结束后，点击发送按钮旁的 `𝄽`，把草稿保存为本浏览器的私人结语。
- [Agent 模式切换](../dsh-preset-switch/README.zh.md)。
  会话空闲时，从标题栏的 preset 名旁打开选择器。

## 安装

需要 DeepSeek Harness 0.2.2-rc.5 及 Web 客户端。

1. 在本目录运行 `pnpm install`，链接工作区中的源插件。
2. 如果目标 profile 已安装成员的独立 bundle，先记下开关状态并移除这些 bundle。
   只关掉插件行仍会留下重复的行 ID。
3. 在 **插件 → 添加插件** 选择本目录。
   确认卡内有三行，再恢复各行的开关状态。

[项目文档](docs/README.md)
