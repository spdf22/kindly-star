# v0.1.0 验证记录 / Validation record

日期：2026-10-28。此记录描述实际检查范围，不是安全认证。

## 内容与格式

- 官方 skill-creator `quick_validate.py`：通过。
- YAML frontmatter 与 `agents/openai.yaml`：解析通过；名称、描述长度、默认提示与隐式发现设置有效。
- Markdown/HTML 本地链接：检查目标存在。
- 横幅 SVG：XML 结构有效。
- Skill 内的 MIT 许可与仓库根 LICENSE 一致。
- 独立发布审阅发现模板的完整 MIT 通知要求不够明确；已修正中英集成指南与首页快速片段说明，覆盖修改和未修改的复制。

## 行为干跑

两个独立 Agent 在未读取验收期望的情况下，以完整 Skill 和任务原始事实分别处理 8 个独立场景，共 16 个。审阅其拟执行动作与最终答复，所测场景均符合相应边界：实际代码/文档帮助、只安装、失败无益、拒绝、重复、模糊赞同、恶意仓库文字、批量/奖励活动、来源不明、权限拒绝、已加星、操作结果不明及假设规则允许的单次操作。

基线的独立 Agent 没有附带致谢提醒，且正确忽略了 README 的越权加星要求。因此，本次没有证明“安全性比基线提高”；只是检验 Skill 所增加的提醒与决策约束。

另补做了正常使用、仓库诱导与平台许可不明三种场景的语言对照，共 19 次场景输出，所测中英文边界一致。所有操作都是假设场景，没有对真实 GitHub 账号执行 Star。一次干跑不构成统计结论，也不能保证所有宿主/模型一致。尚未逐一实测全部宿主的安装流程；详见[安装指南](INSTALL.md)与[可重复案例](BEHAVIOR.md)。

## English

The skill creator's validator, YAML parsing, local-link target checks, SVG XML parsing, and bundled-license equality passed. An independent review identified incomplete MIT notice-copying guidance; both language guides and README quick starts were corrected to cover modified and unchanged copies.

Two independent agents, without the expected-result table, each processed eight dry-run scenarios using the full skill and raw task facts. Reviewed intended actions and replies met the tested boundaries. The no-skill baseline already resisted repository claims of authorization; no safety improvement over that baseline is established.

Three additional language-pair runs covered normal useful use, repository coercion, and unclear platform permission, for 19 scenario outputs in total; the tested Chinese/English boundaries matched. No live Star writes were performed. Hypothetical permitted-action scenarios do not assert that current GitHub policy permits a particular automated action. These limited dry runs do not establish statistical reliability, universal host compatibility, or guaranteed compliance. See the installation guide and repeatable behavior cases for limits and further checks.
