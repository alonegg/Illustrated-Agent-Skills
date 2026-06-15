# 图解 Skill — 配套资源仓库

<img width="500" height="500" alt="66915（立体）" src="https://github.com/user-attachments/assets/6caef6a2-6f11-490e-a43b-e810df8e9354" />

- 京东购买链接：https://u.jd.com/RDY9YwC
- 电子书购买链接：https://www.ituring.com.cn/book/3616

本仓库是图书 **《图解 Skill —— AI 提效实战指南》**（作者：[宝玉](https://github.com/JimLiu)）的配套资源。书里因为篇幅放不下、或者更适合在线查阅的内容都收在这里：附录全文、各章配图与对应提示词、写作工作流技能完整版、章节示例代码与数据、以及生成本书插图所用的技能本身。

> 试读样章见仓库根目录的 [`【试读】图解Skill（前言+目录+第1章部分+第4章部分）.pdf`](./【试读】图解Skill（前言+目录+第1章部分+第4章部分）.pdf)。

## 目录结构

```
.
├── 附录.md                    # 全书附录（术语表 / 安装指南 / 国内平台 / 完整技能）
├── 术语表.md                  # 英文术语与中文译名对照
├── chapters-illutrations/    # 各章配图、提示词、未采用的备选稿
├── skill-templates/          # 第 5 章写作工作流的简化技能模板
├── skills/                   # 完整可用的技能（含生成本书插图的技能）
├── examples/                 # 章节示例代码与数据
├── campaign-data-2025-01.csv # 第 7 章数据分析示例用的样本数据
└── 【试读】….pdf              # 试读样章
```

## 各部分说明

### 1. 附录全文（[`附录.md`](./附录.md)）

书末附录的可在线更新版，包含四个部分：

| 编号 | 内容 | 说明 |
| --- | --- | --- |
| 附录 A | 术语表 | 全书核心术语中英对照 |
| 附录 B | 各平台技能安装指南 | Claude.ai、Claude Code、VS Code、OpenCode 等 |
| 附录 C | 国内模型 API 平台与部署方案 | 百炼、Kimi、智谱、DeepSeek、火山方舟 + OpenClaw 一键部署 |
| 附录 D | 写作工作流及访谈整理工作流完整版技能参考 | 作者日常在用的四个完整技能 SKILL.md |

平台和命令会随时间变化，以这里的在线版为准。

### 2. 章节配图与提示词（[`chapters-illutrations/`](./chapters-illutrations/)）

按章节组织（`preface` 至 `chapter-07`）。每个章节目录下：

- `imgs/` — 书中最终采用的配图（`.webp` / `.png`）
- `prompts/` — 每张配图对应的生成提示词，文件名与图片一一对应
- `bak/` — 同一个位置的备选稿或被淘汰的方案（不是所有章节都有）
- `ref/` — 参考素材（不是所有章节都有）

提示词文件开头以注释形式标注了配图在书中的位置和布局类型，方便对照阅读。这部分也可以当作 **"提示词怎么写"** 的样本库来翻。

### 3. 写作工作流技能模板（[`skill-templates/`](./skill-templates/)）

第 5 章介绍的简化版技能，可以直接复制到自己的技能目录使用：

| 技能 | 作用 |
| --- | --- |
| `content-analyzer.md` | 素材深度分析 |
| `outliner.md` | 大纲生成（多方案） |
| `writer.md` | 写作 |
| `writing-style.md` | 写作风格基调约束 |
| `article-polish.md` | 文章润色 |
| `article-illustrator.md` | 文章配图（简化版） |
| `meeting-analyzer.md` | 会议素材分析 |
| `meeting-minutes.md` | 会议纪要 |

完整版（迭代更细致、串联逻辑更完整）见 [`附录.md`](./附录.md) 的附录 D。

### 4. 完整技能（[`skills/`](./skills/)）

可直接安装使用的完整技能。目前包含：

- [`book-illustrator/`](./skills/book-illustrator/) — **本书所有插图就是用这个技能生成的**。专注于《图解 Skill —— AI 提效实战指南》的章节/附录书稿，一次性分析整篇书稿、批量识别配图位置、subagent 并行出图、自动回写书稿。带 `references/design-system.md`（出版三色调色板、对比规则、反 AI 俗套禁用清单等）和 `prompts/` 子目录。
- [`content-analyzer/`](./skills/content-analyzer/) — 素材深度分析技能。支持文章、推文、视频文稿等多种内容类型，用于理解核心观点与论证逻辑、批判性评估、提取写作素材、分析传播价值。
- [`interview-analysis/`](./skills/interview-analysis/) — 访谈内容分析技能。将播客/视频访谈转化为结构化写作素材包和提纲，提取高价值信息点、金句与待验证背景。
- [`interview-writing/`](./skills/interview-writing/) — 访谈实录写作技能。将访谈分析素材转化为正式文章，保留问答对话感，补充背景解读，适合在完成访谈分析后使用。
- [`outliner/`](./skills/outliner/) — 科技专栏提纲生成技能。根据用户提供的素材生成 3–5 个差异化大纲方案（优先包含故事驱动型），每个方案保存独立文件供选择。
- [`adversarial-polish/`](./skills/adversarial-polish/) — 多轮对抗式稿件打磨技能。通过"批评→改写→综合→盲评"循环，像学术同行评审一样反复打磨稿件直到收敛。**⚠️ 仅供学习研究用，不具备实际使用价值**——该技能依赖 sub-agent 上下文隔离机制，而当前各主流平台均不支持此能力，实际运行效果远不如预期。保留在此仅供读者理解"角色隔离"与"对抗式推理"的设计思路。
- [`info-digest/`](./skills/info-digest/) — 资讯速递技能。把任何输入的信息（新闻、长文、报告、论文、政策、产品资料、链接等）快速转化为简洁、易懂的中文资讯，让读者一两分钟抓住要点。先按信息类型快速拆解（抓核心、补背景、站在读者角度想），需要时联网检索补背景、查事实，再以"说人话、点出跟读者的关系、结尾干脆"为原则撰写纯文本快讯。

安装方法见 [附录 B](./附录.md#附录-b-各平台技能安装指南)。

### 5. 开源技能集（[`baoyu-skills`](https://github.com/JimLiu/baoyu-skills/blob/main/README.zh.md)）

如果想直接使用作者日常维护的通用技能集，可以看开源仓库 [`JimLiu/baoyu-skills`](https://github.com/JimLiu/baoyu-skills)。这是宝玉分享的 AI Agent 技能集，适用于 Claude Code、Codex 等 Agent，覆盖内容生成、AI 生成后端和日常效率工具三类场景。

当前仓库已收录 20+ 个 skill。不要一次性安装全部 skills：每个启用的 skill 都会占用 Agent 的上下文，装得越多，日常调用越容易变慢、变乱。建议先看完整清单，只挑当前工作流真正会用到的几个安装。


```bash
# 快速安装
npx skills add jimliu/baoyu-skills

# 或注册为 Codex / Claude Code 插件市场
/plugin marketplace add JimLiu/baoyu-skills
```

其中包含文章配图、信息图、图表、封面图、幻灯片、知识漫画、Markdown 转 HTML、翻译、YouTube 字幕提取、图片压缩、发布到微信公众号 / 微博 / X 等技能。完整清单和每个技能的用法见 [`README.zh.md`](https://github.com/JimLiu/baoyu-skills/blob/main/README.zh.md)。

### 6. 章节示例（[`examples/`](./examples/)）

书中演示用到的代码、数据与产出。

- [`chapter-07/`](./examples/chapter-07/) — 数据分析技能的三次迭代版本（`data-analysis-v1` → `v2` → `v3`），对照可以看到一个技能是怎么被"用"出来的。`output/` 是运行后的产物。

根目录的 [`campaign-data-2025-01.csv`](./campaign-data-2025-01.csv) 是第 7 章示例使用的样本数据。

## 怎么用这个仓库

- **看书时遇到附录引用** → 直接看 [`附录.md`](./附录.md)，平台和 API 信息以这里为准。
- **遇到不熟悉的英文术语** → 查 [`术语表.md`](./术语表.md) 对应的中文译名。
- **想抄一份配图提示词** → 去 [`chapters-illutrations/`](./chapters-illutrations/) 对应章节的 `prompts/`。
- **想搭一条写作工作流** → 从 [`skill-templates/`](./skill-templates/) 起步，对照附录 D 的完整版迭代。
- **想为本书补图、重画或批量生成章节插图** → 装上 [`skills/book-illustrator`](./skills/book-illustrator/)。
- **想安装作者开源的通用技能集** → 看 [`baoyu-skills`](https://github.com/JimLiu/baoyu-skills/blob/main/README.zh.md)，按需安装少数真正会用到的 skills，不建议一次性全装。
- **想看一个技能怎么演化** → 翻 [`examples/chapter-07/`](./examples/chapter-07/) 的 v1/v2/v3。

## 关于本书

- 书名：图解 Skill —— AI 提效实战指南
- 作者：宝玉
- 反馈与勘误：欢迎在本仓库提 issue

## License

本仓库内容默认遵循书籍授权条款，仅供学习参考。商业使用请联系作者。
