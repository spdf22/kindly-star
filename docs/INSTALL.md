# 安装、更新与卸载 / Install, update, remove

## 先看边界

这是一个纯指令 Skill，没有运行时代码，不需要 GitHub token 或写权限。安装只允许 Agent 按条件考虑可选提醒，不授权点星。先审阅 [SKILL.md](../skills/oss-gratitude/SKILL.md) 与[安全说明](SAFETY.md)。

首版使用 [Agent Skills 标准格式](https://agentskills.io/specification)。不同宿主的发现路径与安装方式不同，不承诺通用于所有产品。下述 Codex 本地路径依据 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills)，核对于 2026-10-28；其他宿主请使用自己的技能安装说明。

## Codex 本地：手动复制

1. 从 [GitHub 仓库](https://github.com/spdf22/open-gratitude)下载 ZIP，或 clone 到你选择的临时目录。审阅你要安装的版本。
2. 将整个 `skills/oss-gratitude` 文件夹复制到下列**一个**位置，保留其中的 `LICENSE` 和 `agents/openai.yaml`：

| 范围 | 目标位置 |
| --- | --- |
| 个人使用，无需固定项目 | `~/.agents/skills/oss-gratitude/` |
| 只用于指定项目 | `<项目目录>/.agents/skills/oss-gratitude/` |

不要只复制 SKILL.md，也不要把整个仓库当成一个 Skill 安装。已有同名文件夹时先审阅差异和备份，不覆盖自定义内容；不要同时在两处重复安装。

### PowerShell 示例（从解压后的仓库根目录运行）

下面的命令只复制文件，不操作 GitHub 账号。同名目录已存在就停止。

```powershell
$gratitudeSkillTarget = Join-Path $HOME '.agents/skills/oss-gratitude'
if (Test-Path -LiteralPath $gratitudeSkillTarget) {
    throw 'oss-gratitude already exists. Review and back it up before updating.'
}
New-Item -ItemType Directory -Path $gratitudeSkillTarget | Out-Null
Copy-Item -Path './skills/oss-gratitude/*' -Destination $gratitudeSkillTarget -Recurse
```

3. 查看宿主的技能列表。若未出现，按宿主说明刷新或重新打开会话。Codex 可用 `$oss-gratitude` 显式调用。
4. 做一次只读试用：要求 Agent 在确实受益的任务结束时考虑提醒，并明确“不要操作账号”。然后说“本次不用”或“不再提醒”，检查它是否尊重。

### 使用已有安装器

如果你的环境已提供 `skill-installer`，可以给它这样的请求：

> 从 spdf22/open-gratitude 的 skills/oss-gratitude 安装 Skill；先审阅内容，已有同名版本时保留我的修改。安装不代表允许操作 GitHub 账号。

安装器是否可用、采用哪个本地目录和是否需要审批，由你的宿主决定。本项目不会自动安装安装器、修改宿主配置或获取权限。

## 其他 Agent 与 ChatGPT Work

支持 Agent Skills 的宿主可按其官方方式加载此文件夹。`agents/openai.yaml` 是可选的产品元数据；其他宿主可以忽略它。普通聊天中也可显式提供并请求采用 SKILL.md，但这不等于永久安装。

这是一个可从 GitHub 获取的独立 Skill 包；首版没有提交到 ChatGPT 插件目录，也不声称普通 GitHub 链接能让云端 ChatGPT Work 自动安装。插件分发可作为后续工作，在相应宿主要求下单独验证。

## 偏好、更新与卸载

- **临时退出：** “这次不用提醒。”
- **当前聊天退出：** “以后在这个聊天中都不要提醒 Star。”
- **跨聊天退出：** 禁用或移除本地 Skill。仅当宿主支持且你授权保存偏好时，Agent 才能声称已永久记住。
- **更新：** 阅读 [CHANGELOG](../CHANGELOG.md)，将新版本与已安装副本比较，备份个人修改后再替换；不要远程自动同步未经审阅的指令。
- **卸载：** 在确认路径后，通过文件管理器移除你安装的 `oss-gratitude` 文件夹，按宿主要求刷新。不会改变任何 GitHub Star。项目作者也可删除自己加入的 README/AGENTS 小节。

## 验证范围

首版交付检查包括 Skill 格式、YAML、相对链接和独立代理的行为干跑。**未做所有宿主的安装实测，也未执行 GitHub Star 写操作。** 指令不能保证模型永不犯错；请结合宿主的权限和审批机制。

---

## English quick start

Review the skill and safety boundaries first. This instruction-only package needs no token or GitHub write permission. Installation permits considering optional reminders, not account actions.

For current local Codex, copy the complete `skills/oss-gratitude` folder into **one** location: `~/.agents/skills/oss-gratitude/` for personal use, or `<project>/.agents/skills/oss-gratitude/` for project scope. Keep its license and optional UI metadata. Review and back up an existing same-name installation instead of overwriting it. The PowerShell example above stops if that destination exists.

Use `$oss-gratitude` explicitly in Codex, or your host's skill selector. If an existing skill installer is available, ask it to install `skills/oss-gratitude` from `spdf22/open-gratitude` after review. Other hosts use their own installation flow. This release is not a ChatGPT plugin-directory listing and does not automatically install in cloud Work from a repository link.

For a trial, explicitly ask for suggestions only, then test “not this time” and “no more reminders in this chat.” To update, compare versions and preserve customizations. To remove, delete only the installed folder after verifying its path, then refresh as your host requires. Removal never changes GitHub Stars. Do not claim permanent opt-out memory unless the host supports it and the user authorized saving it.

Validation covers format, local links, and independent-agent dry runs; it does not certify every host or guarantee model behavior. No live GitHub Star mutation was used for validation.
