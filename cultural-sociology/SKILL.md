---
name: cultural-sociology
version: "1.1.0"
agent_created: true
display_name: 文化社会学
display_name_en: Cultural Sociology
description: "文化社会学知识库与工作流，覆盖三条路线（布迪厄 / 强纲领 / 计算测量），并含计算社会学补编（计算扎根、解释的测量、文化本体论、社会预测）。Use when users ask about cultural sociology concepts, interpretation of social phenomena, research topics, paper writing or review, or computational/computational-social-science approaches to culture. Do NOT use for pure econometric causal inference, literary criticism, or psychological assessment."
description_zh: "文化社会学（Cultural Sociology）知识库与工作流，覆盖三条路线：布迪厄路线（惯习/场域/资本/区隔/象征暴力/边界）、强纲领路线（亚历山大：符码/叙事/文化创伤/公民领域/社会表演/图像权力）、计算测量路线（主题模型/词嵌入/关系网络/文化测量与验证），并含**计算社会学补编**（计算扎根、解释的测量、文化的本体论类型、社会预测与机器学习）。用于：知识科普及概念解释、用文化社会学理论解读社会现象、解答专业问题、系统学习知识点、探讨与评估选题、撰写文化社会学论文（中英文）、评审论文质量、精读文献导读。当用户提到布迪厄、惯习、场域、文化资本、区隔、象征暴力、亚历山大、强纲领、文化创伤、公民领域、社会表演、符码、拉蒙、边界工作、承认、文化分层，或提到计算社会学、计算扎根、社会预测、解释的测量、主题模型、词嵌入、文本分析测量文化时使用。不用于：纯计量因果推断（DID/IV/RDD）、纯文学或艺术批评、心理测量与临床评估、与意义无关的运营数据分析。"
description_en: "A working knowledge base for cultural sociology across three routes: Bourdieu (habitus, field, capital, distinction, symbolic violence, boundaries), the Strong Program (Alexander: codes, narrative, cultural trauma, civil sphere, social performance, iconic power), and computational measurement (topic models, word embeddings, relational methods, validation). Use for explaining concepts, interpreting social phenomena, developing or evaluating research topics, writing and reviewing papers, and guided reading. Do not use for pure econometric causal inference, literary criticism, or psychological assessment."
---

# 文化社会学（Cultural Sociology）

这个 skill 有三条路线、七类任务、一套评分量表。**核心行为只有一条：遇到「解答专业问题 / 学习知识点 / 探讨选题 / 撰写论文」时，先问用户走哪条路线，并把三条路线的差异讲清楚。**

---

## 0. 三条路线速查

| | 布迪厄路线 | 强纲领路线 | 计算测量路线 |
|---|---|---|---|
| 文化是什么 | 被争夺、可兑换的权力资源 | 自足的意义结构，有自身语法与因果力 | 可测量、可比较的意义分布 |
| 关心什么 | 谁得到了什么、为什么能代代相传 | 这件事为什么被理解成这样 | 这种理解有多广、怎么变 |
| 关键概念 | 惯习、场域、资本、象征暴力、区隔、边界 | 二元符码、叙事文类、文化创伤、公民领域、社会表演 | 意义结构、主题、语义维度、关系构型 |
| 典型方法 | 对应分析、场域民族志、生活史访谈 | 厚描、档案与文本编码、过程追踪 | 主题模型、词嵌入、网络与关联规则 |
| 贡献 | 揭穿一个看不见的再生产机制 | 造一个可被别人拿去用的概念 | 给一套可复用的测量 |
| 软肋 | 变迁与能动性 | 可证伪性 | 效度与语境 |

详细对照、提问话术、混合策略 → `references/route-selection.md`
同一现象在三条路线下分别怎么做（四个完整例子）→ `references/route-comparison.md`
计算测量路线的上游补编（本体论／解释测量／人机分工／预测）→ `references/computational-sociology.md`

---

## 1. 路由协议（按序执行）

### 第 1 步：判断任务类型

| 用户请求 | 任务 | 是否问路线 |
|---|---|---|
| 「文化社会学是什么」「什么是象征暴力」 | 科普 / 概念答疑 | 不问，按概念归属直接答 |
| 「用文化社会学解释××现象」 | 解读现象 | **问** |
| 「带我学文化社会学」「列阅读计划」 | 系统学习 | 不问，给三条并行路径 |
| 「我想研究××，有什么选题」 | 选题 | **问** |
| 「帮我写××论文 / 引言 / 理论框架」 | 写作 | **必须问** |
| 「看看这篇论文怎么样」 | 评审 | 先判路线（可用正文判），再评 |
| 「这本书讲了什么」 | 精读导读 | 不问 |

### 第 2 步：需要问路线时，只问一次

按 `route-selection.md` §3.2 的模板发一条消息：一张三列小表（关心什么 / 材料 / 贡献）+ 一句「你更想走哪条」，**不要写成三千字综述**。同时给三条各一句自测题。

### 第 3 步：处理回答

- **选定了** → 读对应路线文件，进入任务流程。
- **「你帮我选」** → 按材料与目标默认（`route-selection.md` §3.5），说明理由，并给一句「换另一条会长成什么样」。
- **「三条都要 / 结合」** → 按 §5 的合法组合给方案（主路线 + 辅助路线），并指出哪一步不能混。
- **「我选 X 但材料像 Y」** → 指出错配，给「换材料」或「换路线」两个选项。

### 第 4 步：进入任务手册

七类任务的输出结构、模板、禁止事项 → `references/task-playbooks.md`

---

## 2. 文件导航（按需读，不要一次全读）

| 文件 | 什么时候读 | 体量 |
|---|---|---|
| `references/route-selection.md` | 需要解释三路线差异、提问、处理混合 | 中 |
| `references/route-comparison.md` | 用户要「解读一个现象」或问「三条路线分别怎么做」 | 中 |
| `references/bourdieu-route.md` | 选布迪厄路线后的全部工作 | 大（609 行） |
| `references/strong-program-route.md` | 选强纲领路线后的全部工作 | 大（688 行） |
| `references/computational-route.md` | 选计算路线后的全部工作 | 大（636 行） |
| `references/computational-sociology.md` | 计算路线的本体论前提、解释测量、人机分工、因果与预测边界 | 中（约 220 行） |
| `references/extensions.md` | 涉及歧视/污名/承认/素质话语/后殖民 | 中 |
| `references/glossary.md` | 任何概念的定义、出处、常见误用 | 大（查，不读） |
| `references/debates.md` | 「谁批评谁」「有没有统一范式」「三派怎么吵」 | 中 |
| `references/canon.md` | 「读什么」「这本书干什么用」 | 中 |
| `references/task-playbooks.md` | 七类任务的操作细节 | 中 |
| `references/review-rubric.md` | 评审论文、自评、打分 | 中 |
| `references/audit.md` | 被问「你读完了吗」「依据是什么」时必须读 | 短 |

**检索建议**：文件较大时用关键词定位，不要通读。常用检索词：`惯习`、`场域`、`文化资本`、`符码`、`创伤过程`、`六要素`、`主题模型`、`词嵌入`、`验证`、`未核实`。

---

## 3. 输出规范（适用于所有任务）

1. **先结论后依据**。第一段就给答案或判断，不要先铺垫三百年学科史。
2. **概念必须落到原作者**：给「中文（English）+ 一句定义 + 谁说的」。检索不到出处就说「我记不清出处」，不要编。
3. **路线标签不可混用**：说「布迪厄认为」就不能接强纲领的主张；跨路线比较时明写「在强纲领看来……」。
4. **区分三种陈述**：
   - 原文事实（可给页码）
   - 学界判断（标明「这是判断/有争议」）
   - 我的推论（标明「这是推论」）
5. **中文正文 + 关键术语英文**（用户习惯）；英文写作时用单作者人称（本文/本研究）。
6. **不写空话**：删掉「具有重要意义」「深刻揭示了」「丰富了相关研究」。

---

## 4. 五条质量红线

1. **零虚构引用**。不确定年份、期刊、页码，就写「（出处待核）」。宁可少引，不可编引。
2. **不用「文化」当万能解释**。凡用「文化原因」收尾的句子，必须给出机制（谁在何时以何方式）。
3. **不把相关当因果**（计算路线尤其）；不把例证当证据（强纲领尤其）；不把「阶层显著」当机制（布迪厄尤其）。
4. **不把「未核实」写成确定事实**。本 skill 里标了「未核实」「判断」「笔记归纳」的内容，转述时必须保留标记。
5. **不做未受请求的动机解读**。用户问「这段文本为什么这样写」，答文本与结构；不要推测作者/用户的心理动机或战略意图。

---

## 5. 常见任务的最短路径

- **「什么是 X」** → `glossary.md` → 定义/出处/反对什么/误用/另一路线怎么看。
- **「解释××现象」** → 问路线 → `route-comparison.md` 找最近例子 → 按 §2 五步输出。
- **「我该读什么」** → `canon.md` §1 入门顺序 → 给 4 周计划（`task-playbooks.md` §3.2）。
- **「有什么选题」** → `debates.md` §5 + `task-playbooks.md` §4 → 3–5 个候选 + 评估矩阵打分。
- **「帮我写论文」** → 问路线 → 对应路线文件 §5/§6 的骨架 → `task-playbooks.md` §5 的篇幅分配与句式。
- **「评这篇论文」** → 判路线 → `review-rubric.md` → 三段评语 + 分数构成表 + 提升路径。
- **「这本书讲什么」** → `canon.md` 找条目 → `task-playbooks.md` §7 七段式导读。
- **「我这套计算算不算文化社会学研究／主题能不能当文化」** → `computational-sociology.md` §2、§7。

## 6. ⚠️ Gotchas

- **不要一上来就给「三条路线综述」**。用户要的是答案，不是教科书。先判断任务，需要时才解释三路线。
- **不要跳过路线提问直接写论文**。写出来的东西会变成三套本体论混在一起的怪物（既有「文化自主」又有「文化是资本的反映」），这是审稿必拒的硬伤。
- **不要把「强纲领」当成「文化很重要」的同义词**。它有明确判据：文化是解释项、重构内部结构、指名 proximate mechanism。
- **不要把「场域」当地域/行业/圈子**。没有位置测量就不是场域分析。
- **不要把「主题模型的结果」叫「符码」**。主题是词共现簇，符码是二元对立结构。
- **不要引用没读过的页码**。本 skill 的页码是 PDF 物理页，只能用于定位，不能替代原文核对。
- **不要用「深层」「建构」「规训」「景观」当形容词**。这些词在中文写作里已被用坏，读者会自动打折。
- **不要在评审时跨路线比较分数**。用计算的标准评强纲领会得出「不可复制」，反之得出「没有深度」——两者都是范畴错误。
- **不要在用户只问一个概念时倾泻整条路线**。先给 200 字答案，再问「要不要展开」。
- **涉及中国经验时要标出前提**。强纲领的「说服机制」预设了可争夺的注意力市场；布迪厄的「文化资本」预设了审美品味被奖励的场域。这两个前提在中国都可能不成立（`strong-program-route.md` §11、`bourdieu-route.md` §10）。
