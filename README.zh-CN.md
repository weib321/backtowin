# BackToWin — 带安全网的 Windows 自动重装

**自动重装 Windows；失败，自动回滚到装前状态。**

BackToWin 使用**微软官方镜像**端到端重装 Windows 10/11——包括微软官方不提供的 Windows 11 → Windows 10 降级。任何一步失败，系统自动回到安装前状态。

- 🏠 官网与文档：<https://backtowin.net>
- 🤖 AI Agent 接入：[backtowin-mcp](https://github.com/weib321/backtowin-mcp)

## 工作方式（三步）

1. **机器体检**——只读采集：Windows 版本、固件（UEFI/BIOS）、磁盘加密状态；Win11 机器可走降级通道。
2. **文件备份**——动手前先给备份清单；回滚保护系统，备份保护你选定的文件。
3. **无人值守重装**——官方镜像对照官方哈希记录核验，**查无哈希记录即拒绝继续**；失败自动回滚。

## 下载

Windows 构建（EN / DE / FR）：**[GitHub Releases](https://github.com/weib321/backtowin/releases/latest)**，每个发布附 md5 指纹并与版本白名单核对。

## 定价

- **免费试用**：1 次重装
- **$6.9**：单次　**$9.9**：3 次
- 码无效：邮件全额退款

## 公示与范围

公开试点中：实测装机统计随积累在官网公示，无档案时如实显示 **Pending**——数字零虚构。BackToWin 只承诺一件事：你的机器**能开机、能上网，双向**。仅此而已。

## 许可

MIT。

## 第三方组件

- 工具内捆绑 [Fido](https://github.com/pbatard/Fido)（GPL-3.0-or-later），用于解析微软官方镜像直链，其许可证文本随包分发。

