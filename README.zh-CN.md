# Clarify First

[English](README.md)

这是一个按需触发的需求澄清流程。遇到信息缺口时，AI 每次只问一个信息点；需求已经清楚时，可以不追问。之后它会给出“需求理解＋拟定方案”，等你确认，再继续完成原始任务。流程只作用于这一个任务，不设固定问题数量上限。

核心内容是 [Skill](plugins/clarify-first/skills/clarify-first/SKILL.md)；外层是可安装、可分享的 ChatGPT/Codex 插件。项目采用 [MIT 许可证](LICENSE)。

## 如何使用

| 平台 | 示例 |
| --- | --- |
| Codex | `$clarify-first 帮我规划并制作个人作品集网站` |
| ChatGPT Work | 在输入框选择 `clarify-first` Skill，再输入任务 |
| Claude Code | `/clarify-first 帮我规划并制作个人作品集网站` |
| 其他聊天模型 | 先配置 [通用提示词](PROMPT.md)，再输入 `clarify-first: 帮我规划并制作个人作品集网站` |

“98% 把握”是对理解程度的要求，不是可精确计算的概率。AI 仍会根据任务复杂度判断是否需要继续问。

## 安装

先下载或克隆本仓库。插件位于 `plugins/clarify-first/`，仓库已包含 `.agents/plugins/marketplace.json`。

- Codex/ChatGPT 桌面端：运行 `codex plugin marketplace add <仓库的绝对路径>`；也可以直接用 `codex plugin marketplace add jackmiao-svg/clarify-first`。重启桌面应用，在插件目录里选择 Clarify First 来源并安装。Codex CLI 可通过 `/plugins` 安装。
- Claude Code：将 `plugins/clarify-first/skills/clarify-first/` 复制到 `~/.claude/skills/clarify-first/`，然后用 `/clarify-first` 调用。
- Gemini CLI：在仓库根目录运行 `gemini skills link ./plugins/clarify-first/skills/clarify-first`，用 `/skills list` 检查是否被发现。
- 不支持 Skill 的模型：按照 [PROMPT.md](PROMPT.md) 把规则放进自定义指令或对话开头。仅输入英文口令、但未提供规则的模型无法自行理解口令含义。

GitHub 公开发布让别人下载和自行安装；若希望出现在 ChatGPT/Codex 官方公开插件目录，还需要另外提交审核。
