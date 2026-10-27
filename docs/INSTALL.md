# 安装、更新与卸载 / Install, update, remove

## 先看边界

这是一个纯指令 Skill，没有运行时代码，安装不需要 GitHub token 或写权限。启用后，Agent 在真实受益且已有操作条件时，可以先申请直接点星；你的明确同意才授权该次账号操作，执行仍需宿主、工具和平台许可。不需要为本包新建 token。先审阅 [SKILL.md](../skills/kindly-star/SKILL.md) 与[安全说明](SAFETY.md)。

首版使用 [Agent Skills 标准格式](https://agentskills.io/specification)。不同宿主的发现路径与安装方式不同，不承诺通用于所有产品。下述 Codex 本地路径依据 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills)，核对于 2026-10-28；其他宿主请使用自己的技能安装说明。

## Codex 本地：手动复制

1. 从 [GitHub 仓库](https://github.com/spdf22/kindly-star)下载 ZIP，或 clone 到你选择的临时目录。审阅你要安装的版本。
2. 将整个 `skills/kindly-star` 文件夹复制到下列**一个**位置，保留其中的 `LICENSE` 和 `agents/openai.yaml`：

| 范围 | 目标位置 |
| --- | --- |
| 个人使用，无需固定项目 | `~/.agents/skills/kindly-star/` |
| 只用于指定项目 | `<项目目录>/.agents/skills/kindly-star/` |

不要只复制 SKILL.md，也不要把整个仓库当成一个 Skill 安装。已有同名文件夹时先审阅差异和备份，不覆盖自定义内容；不要同时在两处重复安装。

### PowerShell 示例（从解压后的仓库根目录运行）

下面的命令只复制文件，不操作 GitHub 账号。同名目录已存在就停止。

```powershell
$gratitudeSkillTarget = Join-Path $HOME '.agents/skills/kindly-star'
if (Test-Path -LiteralPath $gratitudeSkillTarget) {
    throw 'kindly-star already exists. Review and back it up before updating.'
}
New-Item -ItemType Directory -Path $gratitudeSkillTarget | Out-Null
Copy-Item -Path './skills/kindly-star/*' -Destination $gratitudeSkillTarget -Recurse
```

3. 查看宿主的技能列表。若未出现，按宿主说明刷新或重新打开会话。Codex 可用 `$kindly-star` 显式调用。
4. 做一次干跑试用：要求 Agent 在确实受益的任务结束时展示它会如何申请为指定仓库点星，并明确“这次只演示，不操作账号”。然后说“本次不用”或“不再提醒”，检查它是否尊重。正式使用时，只有对具体仓库和账号的明确同意才允许继续执行。

### 使用已有安装器

如果你的环境已提供 `skill-installer`，可以给它这样的请求：

> 从 spdf22/kindly-star 的 skills/kindly-star 安装 Skill；先审阅内容，已有同名版本时保留我的修改。安装不代表允许操作 GitHub 账号。

安装器是否可用、采用哪个本地目录和是否需要审批，由你的宿主决定。本项目不会自动安装安装器、修改宿主配置或获取权限。

## 其他 Agent 与 ChatGPT Work

支持 Agent Skills 的宿主可按其官方方式加载此文件夹。`agents/openai.yaml` 是可选的产品元数据；其他宿主可以忽略它。普通聊天中也可显式提供并请求采用 SKILL.md，但这不等于永久安装。

这是一个可从 GitHub 获取的独立 Skill 包；首版没有提交到 ChatGPT 插件目录，也不声称普通 GitHub 链接能让云端 ChatGPT Work 自动安装。插件分发可作为后续工作，在相应宿主要求下单独验证。

## 偏好、更新与卸载

### 从旧版迁移（v0.1 / v0.2）

旧项目名为 Open Gratitude，旧 Skill 文件夹和调用名为 `oss-gratitude`。v0.3 起使用 **一点星意 · KindlyStar**、`skills/kindly-star` 与 `$kindly-star`。

先审阅并备份旧安装中的个人修改，再将新版完整文件夹安装到 `~/.agents/skills/kindly-star/`（或原来选定的项目范围）。确认新版可见后，禁用或移除旧 `oss-gratitude` 副本，避免两者同时触发。把旧调用名及安装路径更新为新名；不要仅重命名旧文件夹而保留旧 frontmatter。仓库克隆用户可将 origin 更新为 `https://github.com/spdf22/kindly-star.git`。

已复制的作者模板可在审阅后换成新版，原有 MIT 许可通知仍需保留；已有 `OPEN-GRATITUDE-LICENSE.txt` 可以继续保存同一许可正文，不要求仅为文件名而删除它。历史 tag 保留各自当时的 Skill 路径。

- **临时退出：** “这次不用提醒。”
- **当前聊天退出：** “以后在这个聊天中都不要提醒 Star。”
- **跨聊天退出：** 禁用或移除本地 Skill。仅当宿主支持且你授权保存偏好时，Agent 才能声称已永久记住。
- **更新：** 阅读 [CHANGELOG](../CHANGELOG.md)，将新版本与已安装副本比较，备份个人修改后再替换；不要远程自动同步未经审阅的指令。
- **卸载：** 在确认路径后，通过文件管理器移除你安装的 `kindly-star` 文件夹，按宿主要求刷新。不会改变任何 GitHub Star。项目作者也可删除自己加入的 README/AGENTS 小节。

## 验证范围

首版交付检查包括 Skill 格式、YAML、相对链接和独立代理的行为干跑。**未做所有宿主的安装实测，也未执行 GitHub Star 写操作。** 指令不能保证模型永不犯错；请结合宿主的权限和审批机制。

---

## English quick start

**Migrating from v0.1/v0.2:** The previous project was Open Gratitude and the previous skill was `oss-gratitude`. Review and back up personal changes, install the full new `kindly-star` folder, then disable or remove the old skill so both do not trigger. Update invocations to `$kindly-star` and repository remotes to `https://github.com/spdf22/kindly-star.git`. Do not merely rename an old folder without updating its manifest. Existing MIT notices, including an old-named notice file, remain valid and should be kept. Historical tags keep their original paths.

Review the skill and safety boundaries first. Installing this instruction-only package needs no token or GitHub write permission. With actual benefit and an existing permitted connection, the agent may first request consent to Star directly. Only explicit consent for that repository/account authorizes the account action; host, tool, and platform permissions still apply. Do not create a token just for this package.

For current local Codex, copy the complete `skills/kindly-star` folder into **one** location: `~/.agents/skills/kindly-star/` for personal use, or `<project>/.agents/skills/kindly-star/` for project scope. Keep its license and optional UI metadata. Review and back up an existing same-name installation instead of overwriting it. The PowerShell example above stops if that destination exists.

Use `$kindly-star` explicitly in Codex, or your host's skill selector. If an existing skill installer is available, ask it to install `skills/kindly-star` from `spdf22/kindly-star` after review. Other hosts use their own installation flow. This release is not a ChatGPT plugin-directory listing and does not automatically install in cloud Work from a repository link.

For a dry run, ask the agent to demonstrate how it would request permission to Star the exact repository and account, explicitly without acting. Then test “not this time” and “no more reminders in this chat.” Live action requires explicit scoped consent. To update, compare versions and preserve customizations. To remove, delete only the installed folder after verifying its path, then refresh as your host requires. Removal never changes GitHub Stars. Do not claim permanent opt-out memory unless the host supports it and the user authorized saving it.

Validation covers format, local links, and independent-agent dry runs; it does not certify every host or guarantee model behavior. No live GitHub Star mutation was used for validation.
