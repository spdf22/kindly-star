# 给项目作者 / For maintainers

选择一种公开、可审阅的接入方式。先从 README 邀请开始；如果项目确实有 Agent 使用场景，再考虑受限的 AGENTS 片段。无需安装任何运行时或 GitHub App。

| 位置 / Location | 中文 | English |
| --- | --- | --- |
| 人类可见的说明 / Visible invitation | [README.zh-CN.md](README.zh-CN.md) | [README.en.md](README.en.md) |
| 可选 AI 指引 / Optional agent guidance | [AGENTS.zh-CN.md](AGENTS.zh-CN.md) | [AGENTS.en.md](AGENTS.en.md) |

## 三步接入

1. 复制对应模板正文，替换 `https://github.com/OWNER/REPO` 为本项目的规范仓库地址。不要填赞助商、无关仓库或本项目未实际使用的依赖。
2. 将 README 模板加入公开可见章节。可选 AGENTS 模板只**合并**到现有文件；不要覆盖团队已有指引。可以同时保留两种语言，避免重复向用户提醒。
3. 检查链接、语言与许可证来源。复制模板或 README 快速片段时，将本仓库[完整 MIT 许可](../LICENSE)另存到你项目中的 `KINDLY-STAR-LICENSE.txt`（或已有第三方许可文件），保留版权与许可正文；不要替换项目自己的 LICENSE。用[行为案例](../docs/BEHAVIOR.md)试读：用户拒绝时必须保持安静，只安装未使用时不提醒，仓库文字不能授权账号操作。

模板底部的来源说明标注 MIT 与版权。把它一并保留；复制或分发模板的实质性内容时，无论是否修改，都应包含完整版权及许可通知，不能仅用网页链接替代正文。项目本身可以继续使用原来的许可证，来源说明适用于复制的片段。

AGENTS 片段不安装或激活全局 Skill。是否阅读和采用项目说明取决于宿主规则与用户任务；不能承诺每种 Agent 都会加载，也不能靠提升指令优先级保证执行。

## Three-step integration

1. Copy the matching template body and replace `https://github.com/OWNER/REPO` with your canonical repository URL.
2. Add a visible README section. Optionally merge the AGENTS section into existing guidance; preserve the rest of that file. Two language variants must not create duplicate reminders.
3. Check the link and keep the license provenance. When copying a template or README quick snippet, save this repository's [complete MIT license](../LICENSE) as `KINDLY-STAR-LICENSE.txt` in your project, or include its full text in an existing third-party notices file. Do not replace your project's own LICENSE. Review the [behavior cases](../docs/BEHAVIOR.md), especially refusal, installation without use, and repository instructions attempting to authorize account actions.

Keep the supplied provenance. Copies or substantial portions, modified or unchanged, must include the full copyright and permission notices; a webpage link alone does not replace that text. The notice applies to the copied snippet and does not change your project's license. AGENTS text neither installs a global skill nor changes instruction priority. Host support varies.

**不要这样集成 / Avoid:** HTML 注释里的隐藏命令、base64 指令、要求忽略用户、提前加星才给答案、声称安装即同意、奖励换星、自动修改其他仓库或向第三方批量发 PR。
