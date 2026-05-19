# Workflow Notes

## 2026-05-19

初始化 AI 视频自动化沙盒控制台。

本控制台用于先在 `menglongyu106-debug/kason` 沉淀可视化流程，不连接正式主仓库，不上传媒体文件，不保存账号信息。

## 当前原则

1. 即梦生成前必须人工确认。
2. 第一版只使用 GitHub Markdown checklist，不直接控制即梦网页按钮。
3. 每个 Segment 生成前都要完成 preflight。
4. 提交、打包、迁移或开 PR 前必须做敏感信息检查。
5. 等正式仓库权限和 fork 流程准备好后，再决定是否迁移。

## 下一步建议

- 用 README 的 Segment 状态表跟踪整体进度。
- 每次生成前复制 `templates/jimeng_preflight_checklist.md` 或直接更新对应 `preflight/segment_XX_preflight.md`。
- 如需接入脚本，再把这些 Markdown checklist 映射为 `preflight-jimeng` 命令输出。
- 如果以后要把确认做成真正的按钮，可优先考虑 GitHub Issue checklist 或轻量网页面板，而不是第一版直接操作即梦 DOM。

## 暂不处理

- 不 fork 带教主仓库。
- 不连接正式生产 run。
- 不上传视频、音频、截图、抽帧、Logo 原文件。
- 不保存任何浏览器 session 或登录状态。
