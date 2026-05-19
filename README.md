# AI 视频自动化沙盒控制台

这是柱坤用于验证 AI 视频自动化流程的临时 GitHub 可视化控制台。

> 重要说明：本仓库只是临时控制台，不是正式生产仓库，也不是带教主仓库的 fork。当前不连接 `yayathink00-png/VIP-THINK-Project`，不上传媒体文件、不上传账号信息、不保存浏览器登录状态。

## 当前目标

把一次 AI 视频制作流程整理成可复用的半自动生产线：

1. 生成前人工确认创作要求、提示词和操作状态。
2. 用 `preflight-jimeng` 检查即梦生成前风险。
3. 生成后下载到沙盒目录，由人工审核。
4. 通过敏感信息扫描后，再考虑提交、迁移或 PR。

## 工作边界

- 临时控制台仓库：`menglongyu106-debug/kason`
- 沙盒 run：`data/runs/sandbox-zhukun-20260518-vipthink-test`
- 即梦测试对话名：`VIP THINK Test - Zhukun - 20260518`
- 正式生产 run 不修改：`data/runs/20260515-162712-jh-v10-解决学习问题-繁體-台灣-口播-横版-800x1000-202501`

## Segment 状态

| Segment | Preflight | 人工确认 | 生成 | 下载 | 人工审核 | 备注 |
|---|---|---|---|---|---|---|
| Segment 01 | 未开始 | 未确认 | 未开始 | 未开始 | 未开始 | 沙盒测试用 |
| Segment 02 | 未开始 | 未确认 | 未开始 | 未开始 | 未开始 | 沙盒测试用 |
| Segment 03 | 未开始 | 未确认 | 未开始 | 未开始 | 未开始 | 沙盒测试用 |
| Segment 04 | 未开始 | 未确认 | 未开始 | 未开始 | 未开始 | 沙盒测试用 |
| Segment 05 | 未开始 | 未确认 | 未开始 | 未开始 | 未开始 | 沙盒测试用 |

更详细的表格模板见 [`templates/segment_status_table.md`](templates/segment_status_table.md)。

## 生成前总检查

每个 Segment 生成前都必须完成以下检查：

- [ ] 确认在正确即梦对话：`VIP THINK Test - Zhukun - 20260518`
- [ ] 确认是视频生成模式
- [ ] 确认比例为 9:16
- [ ] 确认时长为 15 秒
- [ ] 确认无字幕、无花字、无 Logo
- [ ] 确认提示词对应当前 Segment
- [ ] 已收到人工确认：`确认生成 Segment XX`

单段检查模板见 [`templates/jimeng_preflight_checklist.md`](templates/jimeng_preflight_checklist.md)。

## 敏感信息安全线

提交、打包、迁移或开 PR 前，必须确认没有上传：

- 环境配置文件
- 钉钉机器人地址或签名密钥
- 即梦账号、Cookie、浏览器 session 或登录状态
- 原视频、AI 生成视频、音频文件
- 截图、抽帧图片、Logo 原文件
- access token、API key、密码或任何真实凭据

敏感信息检查模板见 [`templates/sensitive_scan_checklist.md`](templates/sensitive_scan_checklist.md)，占位报告见 [`reports/sensitive_scan_report.md`](reports/sensitive_scan_report.md)。

## 可视化查看方式

- 仓库首页：直接看本 README 的状态表和检查项。
- 单段 preflight：打开 [`preflight/`](preflight/) 下对应 Segment 的 Markdown 文件。
- 模板：打开 [`templates/`](templates/) 查看可复制的 checklist。
- 工作记录：打开 [`docs/workflow_notes.md`](docs/workflow_notes.md)。

## 后续迁移说明

等正式仓库权限、fork 或 sparse checkout 流程准备好后，再把这里确认过的模板和流程迁移到正式仓库。迁移前必须重新做敏感信息检查，并且只迁移 Markdown、JSON 模板、脚本和小型文本报告。
