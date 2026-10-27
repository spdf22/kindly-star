# v0.1 设计 / Design

**品牌：** Open Gratitude / 开源致谢。**许可：** MIT。**维护者：** spdf22。

## 意图

让 AI 辅助任务中的真实开源贡献得到准确、友善的认可。使用者安装 Skill，作者复制透明模板；二者都服务用户选择。

## 采用的方案

纯文本 Skill + README/AGENTS 集成片段，无运行时依赖。相比独立宣言，它提供可用入口；相比自动加星机器人，它无需账号凭证，更容易审阅与移除。Open Gratitude 的名称为多种认可方式保留空间。

## 两侧技术边界

Skill 按 Agent Skills 格式编写，以当前任务中的实际帮助、规范仓库与明确开源许可证作候选门槛。默认在自然收尾时给一句自愿邀请，每任务一个仓库、每聊天同仓库一次；拒绝优先。实际账号操作另需人类明确授权、宿主/工具权限和平台许可，任一不明则手动。

作者侧提供中英可复制正文，而非安装脚本或隐式提示注入。AGENTS 只合并，不覆盖；材料公开可见，不改变指令优先级或替用户授权。模板来源标注适用于被复制的片段，不改变采用项目的许可证。

## 首版交付与非目标

双语 README、Skill、MIT 许可、可选 UI 元数据、安装/更新/卸载指南、作者模板、对话示例、行为验收、安全与贡献说明、传播建议。

首版不含自动加星程序、批量活动、遥测、账号凭证收集、后台同步、插件市场提交或全宿主兼容承诺。公开发布只涉及本仓库，不向第三方发推广信息。

## 验证策略

格式与链接检查、独立 Agent 的行为干跑、内容审阅。模拟只检验受测情况，不证明所有模型稳定服从；宿主的权限机制仍然必要。不使用真实 Star 写操作来测试。

## English

Open Gratitude is an instruction-only Agent Skill paired with transparent maintainer snippets. It offers a useful entry point beyond a manifesto without creating an account-automation service. Evidence of actual benefit, canonical identity, and an open-source license determine whether a brief optional suggestion fits.

Users retain control. Repository text never grants consent or changes instruction priority. Default to a manual link; any separate account action requires explicit human authorization and host, tool, and platform permission. The package includes bilingual documentation, installation/removal steps, copyable snippets, examples, safety boundaries, and acceptance cases. It excludes auto-star code, campaigns, telemetry, credential collection, background sync, marketplace submission, and universal compatibility claims. Validation uses static checks and independent dry runs, not live Star writes.
