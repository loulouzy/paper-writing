# paper-writing

学术论文写作与润色 skill，基于 Huang & Ding 的《[Writing AI Conference Papers: A Handbook for Beginners](https://github.com/hzwer/WritingAIPaper)》方法论，面向 CVPR / NeurIPS / ICML / ACM 系列等 AI 顶会。核心信条来自李飞飞：**"Badly written papers get bad reviews. Period."**

An academic paper writing & polishing skill based on Huang & Ding's *[Writing AI Conference Papers: A Handbook for Beginners](https://github.com/hzwer/WritingAIPaper)*, targeting top-tier AI venues (CVPR / NeurIPS / ICML / ACM series). Core creed, from Fei-Fei Li: **"Badly written papers get bad reviews. Period."**

## 安装 / Install

通过 npm 下载 / Download via npm:

```bash
npm install @mulou/paper-writing
```

安装后把 SKILL.md 复制到你的 agent skills 目录 / After install, copy the SKILL.md files into your agent's skills folder:

```bash
# Claude Code (英文版 / English)
cp -r node_modules/@mulou/paper-writing/paper-writing ~/.claude/skills/
# Claude Code (中文版 / Chinese)
cp -r node_modules/@mulou/paper-writing/paper-writing-zh ~/.claude/skills/
```

不想装依赖，可用 npx 直接取包内文件路径 / Or grab the files without a dependency via npx:

```bash
npm pack @mulou/paper-writing   # 下载 tarball，解压即得两个 SKILL.md
```

## Skills

| Skill | 语言 / Language | 说明 / Description |
|---|---|---|
| [`paper-writing`](paper-writing/SKILL.md) | English | Draft, polish, and self-review conference paper sections |
| [`paper-writing-zh`](paper-writing-zh/SKILL.md) | 中文 | 起草、润色、自查论文章节（与英文版内容一致；论文正文仍用英文，解释和报告用中文） |

## 三种工作模式 / Three Working Modes

| 模式 / Mode | 触发场景 / Trigger | 产出 / Output |
|---|---|---|
| **polish 润色** | 提供已写好的段落/章节/全文 / You provide written text | 修改后的文本 + 逐条修改理由 / Revised text + itemized rationale |
| **draft 起草** | 提供想法、实验结果、素材 / You provide ideas and results | 符合规范的英文学术文本 / Publication-quality English text |
| **review 自查** | 要求检查论文、模拟审稿人 / You ask for a check or mock review | 按清单逐项审查的报告 / An item-by-item audit report |

## 方法论要点 / Methodology Highlights

**写作骨架（draft 模式）/ Drafting skeleton:**

- **三层自足结构** — Abstract、Introduction、Main body 每层都要独立讲完整个研究故事；先写 main body，再收缩。
  *Three self-contained levels — abstract, introduction, and main body must each tell the full story; write the main body first, then compress.*
- **贡献三分类（Nowozin）** — 核心贡献必属于 Insight（解释现象）/ Performance（做得更好）/ Capability（首次做到）之一，起草前先定位。
  *Nowozin's taxonomy — every contribution is Insight, Performance, or Capability; position it before drafting.*
- **CARS 三步 Introduction（Swales & Feak）** — 确立领域 → 找到 gap → 占据 niche。
  *The three-move introduction: establish the territory → find the niche → occupy it.*

**可读性四维度（polish 模式的评判标准）/ Four readability dimensions (polish criteria):**

1. **逻辑强度 / Logical Strength** — 逻辑连贯来自逻辑本身，不来自连接词；禁止用 "to this end"、"first of all" 制造不存在的关系。
2. **可辩护性 / Defensibility** — 每句话假想审稿人挑刺；陈述必须有文献和事实支撑，区分直接/间接证据的措辞。
3. **困惑时间 / Confusion Time** — 最小化读者从"这是什么"到"哦，懂了"的时长；概念就近解释、消除代词歧义、多用主题句。
4. **信息密度 / Information Density** — 尽快切入正题；重要解读紧贴图表；宁可重复 baseline 数字也要让对比一目了然。

**审查清单（review 模式）/ Review checklists:**

- 写作质量清单（图表自明性、符号一致性、详略平衡等）
  *Writing-quality checklist (self-explanatory figures, notation consistency, detail balance, ...)*
- 提交前最后检查（`??` 引用错误、图表提及顺序、匿名检查等，可对 LaTeX 工程直接执行）
  *Final pre-submission check (broken `??` references, figure mention order, anonymity, ... — runnable directly on a LaTeX repo)*
- 审稿人视角预演：按六类常见负面意见逐类排查并给出修法
  *Reviewer-perspective rehearsal against six common categories of negative comments, each with its fix*

所有模式下，skill 都会主动指出 **overclaim**（陈述超出实验证据支撑范围），即使你没有要求检查这一点。
In every mode, the skill proactively flags **overclaiming** — statements exceeding what the evidence supports — even when not asked.

## 使用方法 / Usage

将 skill 目录放入你的 agent 的 skills 目录（例如 Claude Code 的 `~/.claude/skills/`，或 Codex 的 `~/.codex/skills/`）。每个 skill 是一个包含 `SKILL.md` 的目录，frontmatter 中的 `description` 描述触发条件，供 agent 自动匹配加载。

Place a skill directory into your agent's skills folder (e.g. `~/.claude/skills/` for Claude Code, or `~/.codex/skills/` for Codex). Each skill is a directory containing a `SKILL.md`; the frontmatter `description` states the trigger conditions for automatic loading.

两个版本的规则完全一致，区别只在与用户交流的语言（论文正文始终用英文写作）。按对话语言选择版本，或两个都装。

The two versions enforce identical rules and differ only in the language used to talk to the user (paper text is always written in English). Pick the one matching your conversation language, or install both.

## 致谢 / Acknowledgments

方法论来自 / Methodology from: Huang & Ding, *Writing AI Conference Papers: A Handbook for Beginners* ([GitHub](https://github.com/hzwer/WritingAIPaper)).
