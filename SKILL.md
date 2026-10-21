---
name: sociology-paper-writing
version: "1.1.0"
display_name: 社会学论文写作
display_name_en: Sociology Paper Writing
description: >-
  手把手指导从选题、标题、摘要、引言、文献综述、研究设计、实证分析到结论与讨论，以及期刊选择与投稿适配的完整社会学/社会科学学术论文写作。Use when 用户要写、改、拆一篇社会学或社科实证论文，或需要某一环节的写作步骤、可复制模板、自查清单与反模式。Do NOT use when 用户只想要纯格式排版或只想做文献数据库检索；本技能不替用户编造文献或数据。
description_zh: >-
  手把手指导从选题、标题、摘要、引言、文献综述、研究设计、实证分析到结论与讨论，以及期刊选择与投稿适配的完整社会学/社会科学学术论文写作。适用：写/改/拆社会学或社科实证论文，或需要某一环节的写作步骤、模板、自查清单与反模式。不适用：纯格式排版、纯文献检索；不编造文献或数据。
description_en: >-
  Step-by-step guidance for writing a complete sociology/social-science paper, from topic, title, abstract, introduction, literature review, research design, empirical analysis, and conclusion/discussion, to journal selection and submission fit. Use when writing, revising, or deconstructing a sociology paper, or needing section-level steps, templates, checklists, and anti-patterns. Do NOT use for pure formatting or literature-database search; never fabricates references or data.
---

# 社会学论文写作（手把手指南）

把你从"想写"带到"写完且像样"。本技能按**论文写作环节**组织，每一环都可单独调用、单独精修。

## 何时使用 / How to use
- 用户说"帮写摘要""改引言""文献综述怎么写""指导我写实证分析""从选题到成稿""投哪本刊" → 加载对应 `references/` 章节。
- 用户给一篇论文求"诊断 / 拆解 / 模仿" → 用各 `references/` 做逐节体检（每节都有自检清单）。
- 不带参数 → 先问想写哪一部分，或直接给 `cheatsheet.md` 速览骨架。

## 核心方法论（贯穿全篇的骨架）
- **洋八股八部分**（彭玉生）：问题 → 文献(理论) → 假设 → 测量 → 数据 → 方法 → 分析 → 结论。经验社科论文的通用呈现骨架；质性/理论研究可省后五股，但**前三股（问题 / 文献 / 假设或论点）不可省**。
- **证明性写作**（张静）：论点 + 论据，基于事实；先有"问题意识"与"论证逻辑"，再谈文采。
- **论点句(thesis)控制全文**（Jones / Becker）：每一节都要能回溯到你的核心问题 / 论点；thesis 像与读者的契约。
- **文献综述 = 论证不是报告**（Machi）：用 map + argument 构建立场，而非罗列书单。
- **写作可习得、靠重写**（Becker）：先写任何粗糙草稿，后多稿修订；匀速(海龟)胜最后一刻。
- **读者能量模型**（易莉）+ **Strunk 18 条**：省句法能量、留语义能量；主动 / 肯定 / 具体 / 删冗余。
- **先定期刊再动笔**（Martín）：没有通用好论文，好论文是"为某本期刊而写"。

## 章节索引（references/）
| # | 章节 | 关键抓手 |
|---|---|---|
| 01 | [选题与研究问题](references/01-选题与研究问题.md) | 好问题四标准、问题意识、从现象到可答问题 |
| 02 | [标题](references/02-标题.md) | 直接 / 清晰 / 简明、陈述句 |
| 03 | [摘要](references/03-摘要.md) | 问题 + 结论 / 发现；Martín 六条 |
| 04 | [引言](references/04-引言.md) | 开门见山、立靶子；Kail 五种钩子 |
| 05 | [文献综述](references/05-文献综述.md) | 六步法、map + argument、选择性但公正 |
| 06 | [研究设计](references/06-研究设计.md) | 理论框架 / 假设 / 变量操作化 / who-what-how |
| 07 | [实证分析](references/07-实证分析.md) | 先报结果再解释、表文配套、完整故事 |
| 08 | [结论与讨论](references/08-结论与讨论.md) | 发现 + 理论含义 + 局限 |
| 09 | [学术语言与风格](references/09-学术语言与风格.md) | 能量模型、Strunk 18 条、去 AI 腔 |
| 10 | [写作流程](references/10-写作流程.md) | 去神秘化、先写方法结果、多稿修订 |
| 11 | [期刊选择与投稿适配](references/11-期刊选择与投稿适配.md) | 先定期刊、IMRaD vs IBC、相关性三支柱 |

## 模板与清单
- 各节可直接复制的模板见 `assets/templates/`（选题 / 标题 / 摘要 / 引言 / 文献综述 / 研究设计 / 实证分析 / 结论与讨论 / 写作流程 / 期刊选择）。
- 速查与逐节自检见 `cheatsheet.md`。

## 工作流建议（完整跑一遍时）
1. **先定期刊**（11）——决定写什么、怎么写、多长。
2. 定**研究问题**（01），再定**标题**（02）。
3. 同步推进**文献综述**（05）与**研究设计**（06）——二者互相塑形。
4. 把**方法 / 结果**先写出来（10：阻力最小、最易有成就感）。
5. 回头写**引言**（04）与**摘要**（03）——此时你已知道全文在说什么。
6. 写**实证分析**（07），再写**结论与讨论**（08）。
7. 全程用**语言与风格**（09）做句子级润色与去 AI 腔。

## ⚠️ Gotchas
- **绝不替用户编造文献或数据**；引用必须真实可查，参考文献零虚构（用户硬规则）。
- 洋八股是"呈现结构"不是"研究过程"；别逼用户按八股顺序动笔（可从方法/结果先写）。
- 文献综述最易写成流水账 / 教科书——坚持 map + argument（见 05）。
- 摘要别写成背景介绍；必须含"问题 + 结论"；**摘要 ≠ 引言的复制粘贴**。
- 实证分析别把"相关"当地"因果"；控制变量 / 稳健性 / 识别策略要交代。
- 结论别引入前文没出现过的新文献 / 理论（应整合进文献综述）。
- 中文长句嵌套最耗读者能量——用易莉能量模型砍从句、用 Strunk 删冗余。
- 引言避免道德说教 / 过度戏剧化 / 耸动；**引言放到全文写完后再写**（Edwards）。
- 投稿前先读目标刊投稿指南与字数；避免一稿多投 / salami slicing。

## Scope & Limits
覆盖学术写作的"怎么写"（结构 / 逻辑 / 语言 / 流程 / 投稿适配）。**不替代**统计软件操作、文献数据库检索、查重，以及特定期刊的硬格式（那些用专门工具）。

**依据来源（17 份）**：
- 第一轮 12 份（桌面「社会学写作」）：彭玉生《洋八股与社会科学规范》、张静《社会学论文写作指南》、刘西川《实证论文写作八讲》、风笑天《看实例、学方法》、Machi & McEvoy《The Literature Review: Six Steps to Success》、Becker《Writing for Social Scientists》、Jones《Writing for Sociology Guide》、易莉《学术写作原来是这样》、Strunk《The Elements of Style》、两篇"如何读社科/定量期刊论文"、董晨宇《拆论文》。
- 第二轮 5 份（桌面「新建文件夹」）：Martín《How to Write a Good Article》(Current Sociology)、Sage《Writing an article for Sociology》、Edwards《Writing in Sociology, 2e》、Kail & Kail《Effective Writing for Sociology》、史密斯-洛温 & 莫斯科维茨《社会学写作指南》。

**如实说明两处机读缺口**：① 董晨宇《拆论文》因字体编码在本环境机读为乱码，其"拆解范文学写作"主题已由其余来源覆盖；② 史密斯-洛温《社会学写作指南》为纯扫描件（无文本层），已启动 OCR 补读，本轮补入前 4 份可读新源为主，OCR 完成后可再增补。
