# 计算测量路线（Computational Cultural Sociology / Measuring Culture）

> **一句话定位**：它不主张「文化可以被算尽」，而主张**解释是有模式的（interpretation is patterned）**，因此可以把解释的外化产物（文本、编码、选择、连线）压成保结构的表征，在**明确划定的局部意义系统**内做可复核、可失败、可累积的比较；技术只是这套认识论承诺的下游，代价是每次测量都必然丢掉信息，而且丢得对不对只能靠外部证据判定。

> **最适合回答的问题**：某类话语、框架、分类图式或评价维度在**一段时间、一个平台、一个场域内**的相对位置与分布如何变化；两个群体是否共享同一套区分逻辑；一个粗糙的文化标签（「爱听金属」「读小说」）内部是否存在有社会意义的亚型；某个概念的意义是否在漂移、往哪个方向漂；一项干预改变的是「谈多少」还是「怎么谈」；自报的文化广度里有多少是知识、多少是「觉得自己有权说」。
> **不适合回答的问题**：意义在具体互动中如何被现场生产（转强纲领的诠释学或民族志）；行动者为何觉得某个意义「理所当然」（转布迪厄的惯习与场域，尽管可用对应分析搭桥，见 §9）；文化与制度后果之间的长时段因果（本路线只能给出候选关联与测量，不能给因果）；小样本、体裁混杂、无稳定对立词的语料上做「语义几何」；以及任何需要回答「这个文本到底在说什么」的问题——那要靠读，不靠算。

> **依据说明**：本底稿只使用带页码的精读笔记，页码一律为 **PDF 物理页（`PDF p.n`）**，不是书内页码。
> - `compute-books-1.md`：Mohr 等《Measuring Culture》(2020) 约正文 38%；Stoltz & Taylor《Mapping Texts》(2024) 约 15%；Grimmer 等《Text as Data》(2022) 约 10%；Silge & Robinson《Text Mining with R》(2017) 约 9%。
> - `compute-books-2.md`：Manovich《Cultural Analytics》(2020) 约正文 40%；Siddiqui《Cultural Analytics in R》(2025) 约 20%；Chen 等《Machine Learning in Social Science》(2026) 约 20%；景永霞等《Python 中文文本分析》约 20%（OCR 缺代码块）；两本工具书仅索引式阅读（PDSH 约 2%、Müller & Guido 约 5%）。
> - `compute-articles.md`：12 篇方法论文，精读 55%–100%（各篇范围见该笔记）。
> - 第 9 节另用 `bourdieu-articles.md`（DiMaggio & Mohr 1985 约 85%、Peterson 1996 相关段、Wang & Tai 2025 全文）与 `strong-books-3.md`（2019 手册第 9 章、第 8 章、第 1 章相关段）。
> - **凡笔记标「未核实」，此处照标**；凡属本底稿的归纳、降级方案或中国场景建议，标「（判断）」；凡笔记本身是转引，标「（转引）」。
>
> **本文件只管技术与验证。** 本体论前提、解释的概念拆解、人机分工、因果与预测的边界，见补编 `computational-sociology.md`（依据 8 份计算社会学文献，精读约 90%）。

---

## 1. 三十秒定位

**它把文化当成什么来测？** 当成**三层上的模式**，而不是一个东西。2020 年那本书的骨架是三个起点——人（people）、物（objects）、社会关系（social relationships）——作者明确说这只是「three intertwined approaches to measurement—three starting points」，并且「we do not think that the separation among these analytic strategies reflects the structure of the social world」（PDF p.147）。与之配套的是一对张力：**解释与测量的二重性（duality of interpretation and measurement）**——「To put it in its strongest form, there can be no measurement of culture without interpretation.」（PDF p.15）。三层是分析性的，不是本体论的；研究要在层次之间来回移动，这叫**枢轴（pivots）**（PDF p.153–155）。

**可测性的许可证从哪来？** 不来自「意义有边界」，而来自「解释有模式」：作者先引 Gary Alan Fine 的警告（文化不是一团无形的雾），再反转——「While some of us see ourselves as card-carrying interpretivists, we also assume that interpretation is patterned, and that these patterns can be analytically captured and translated into measurable form—albeit to varying degrees, and always at some cost.」（PDF p.14）。同时立一个**谨慎的实在论（wary realism）**：数据「represents—however imperfectly—real things and processes」（PDF p.25）。这两句合起来否掉了两个极端：文化不是不可测的雾，测量也不是真理。

**与布迪厄最根本的分歧在哪一句？** 不在「要不要关系」，而在**关系与属性能否平权**。这本书大量继承场域、资本分布、对应分析（PDF p.113、p.116），但作者在第 4 章末尾说本章「remained agnostic about the interaction between relations and attributes」（PDF p.118）——即**不接受**「变量社会学在本体论上必然是扭曲的」这一强命题。布迪厄要求先建构关系空间、属性只是位置的产物；这条路线的做法是：关系与属性都是可用的测量入口，选哪个取决于问题，不取决于本体论。

**与强纲领最根本的分歧在哪一句？** 在**文化有没有自身语法**。强纲领要求文本由先于它、并约束它的二元符码组织；这条路线把意义拆成可测的图式、叙事、实践、评价维度，其技术底座（词袋→主题/嵌入）假定「文本生成主题」，方向正好相反。LDA 原文自己就划了线：「we make no epistemological claims regarding these latent variables beyond their utility in representing probability distributions on sets of words」（Blei et al. 2003, PDF p.4 注 1）。**这句免责声明是整条路线与强纲领之间最诚实的一块界碑**。

**它不宣称什么（先划三条界）**：① 不宣称标准化是目标——「Standardization is not the goal; rather, we seek productive dialogue across different ways of tackling measurement problems」（Mohr et al. 2020, PDF p.25）；② 不宣称计算化等于进步——被访谈的三位学者里「none of the research trajectories… begin with hermeneutic approaches and evolve into increasingly formalized proofs」，反而是「the push to formalize measurement… only amplified the need for more hermeneutic work」（PDF p.152）；③ 不宣称这是混合方法宣言——「This book is not merely another call for the integration of qualitative and quantitative traditions」（PDF p.16）。

---

## 2. 测量的认识论：先定坐标，再选技术

### 2.1 三层（人 / 物 / 关系）× 一对张力（interpretation / measurement）

**三层各自的入场券不同**，这是选技术前必须先看清的：

| 层次 | 文化的形态 | 可测的前提 | 代表技术 | 该层自己的边界难题 |
|---|---|---|---|---|
| **人（people）** | 图式（schema）：「underlying frameworks… link these unit elements into an organized network of associations」（PDF p.33）；以及目标（aims）与集体叙事（collective narratives）（PDF p.42） | 意义在人身上是**关系性**的，所以测「区分逻辑」而不是「取值」 | 关系类别分析（RCA）：把每个受访者的作答当向量，**忽略方向与 valence**，用绝对值差之和算距离再聚类（PDF p.39–40） | 「说」与「做」的错位；作者修正 Vaisey 的双过程模型，明确「there is no one-to-one or mutually exclusive mapping between methods and deliberative or nondeliberative thinking processes… we can only make relative, not absolute comparisons」（PDF p.34） |
| **物（objects）** | 客体化的文化：「both a subjective reality embodied in persons and an objectified reality out in the world」（PDF p.24） | 「To measure a cultural object, it must be durable.」（PDF p.66） | 物件关系测量的四个子类：对象间关系；解释如何影响后续对象生产；物件在人群中的扩散；物件被用来传播观念与标识类别（PDF p.78） | 物件不自带意义：可测的是**affordance**（PDF p.148），且「their interpretation and use are contextual, and their material properties as objects are unstable」（PDF p.150）；必须 in situ 地测（PDF p.66–67） |
| **关系（social relationships）** | 分类即网络（接 White：「categorization is constitutive of social networks」，PDF p.23；Emirbayer 的「反类别律令」，PDF p.92） | 先有边界规则，才有网络 | 二模网络、块模型与结构等价（PDF p.33–34）、对应分析／几何数据分析（PDF p.116）、伽罗瓦格（该书研究手法清单所列，具体页码未核） | 「意义的无限性」被边界技术驯服：网络边界怎么划才既涵盖意义系统又不弥散（PDF p.148–149）；场域之间「in the space between the fields」发生什么（引 Eyal，PDF p.149） |

**一对张力怎么用**：不是「先解释再测量」的先后次序，而是一个循环——任何测量都已经是一次解释（选择切分、停用词、K、轴），任何解释要可比较就必须被外化。外化的哲学依据是 Ricoeur 的**二阶外化（second-order externalizations）**：田野笔记、访谈转写把意义固定为文本，「even data produced within the most qualitative traditions… become amenable to more quantitative techniques as soon as they are externalized」（PDF p.15）。同一论证在 2010 年那篇里被推得更远：形式模型之于文本，正如文本之于言语（Mohr & Rawlings 2010, PDF p.39–41）。

**代价要写在明处**：测量是「necessary reduction of information」（PDF p.25），且「every representation is good for something, but not for everything」（PDF p.26）。作者自己给这条路线的两条边界是**潜在性（potentiality）**——「latent qualities that might lie dormant… which may or may not be activated」（PDF p.149）——与**缺席（absence）**——「the empty spaces of relationships, networks, and fields, as well as what is left unsaid and unthought」（PDF p.150）。Biernacki 的讥讽（一个只出现一次、甚至从未出现的词可能是故事里最重要的词）被作者接受并升级为议程：「How could we capture such a luminous absence?」（PDF p.151）。

### 2.2 Mohr & Rawlings 的 2×2 范式格（四格各把「意义」放在哪）

**两刀不是「量化/质性」，也不是「新/旧」**。第一刀切**因果方向**：文化是否**构成（constitutes）**物质、实践、结构，而非被它们决定（PDF p.9–10）。第二刀切**研究目的**：是用形式工具撬开文本的读法，还是造一个能塞进别的解释框架的稳健度量——判据原句是「Practitioners of the former sort want to use formal tools to make interpretations, to unlock useful readings of texts. Those of the latter persuasion seek robust measures of cultural forms that can be fitted onto other explanatory frames.」（PDF p.2）。解释学（hermeneutic）一词直接采用 Ricoeur 的定义：「the rules required for the interpretation of the written documents of our culture」（Ricoeur 1971: 197，转引 PDF p.14）。

**四格**（注：原文 Table 1／Table 2 在 txt 中为图片，未进入文本层；以下格位由正文 p.12–36 逐节陈述复原，不是抄表）：

| | **前文化转向（pre-cultural turn）** | **后文化转向（post-cultural turn）** |
|---|---|---|
| **非解释学（non-hermeneutic）** | **格 A：Kroeber**。量 1844 年起女装晚礼服的 8 个尺寸（4 长 4 宽），以「嘴到脚尖」为基准算比值，每年 10 张图，画出百年周期波（PDF p.16–19）。**意义在物件的风格变异里**，且变异由文化之外的力（「super-organic」）驱动；文章里没有一个穿衣的人。判词：「In Kroeber's essay culture is everywhere and nowhere.」（PDF p.20） | **格 C：DiMaggio**。1982 年用因子分析把文化资本做成可进回归的变量（β=.1636\*\*\*，ΔR²=.0310，PDF p.26）。**意义在被测物与「真正的」意义之间的指涉关系里**——博物馆访问「反映」文化资本，但反映的是什么不被测：「Not meanings, not understandings... are being modeled」（PDF p.28）。 |
| **解释学（hermeneutic）** | **格 B：Lévi-Strauss**。神话分析把句子排成行（讲述顺序）与列（关系束），读懂要「ignore one half of the diachronic dimension... and read from left to right, column after column」（PDF p.23）。**意义在关系束的对立结构里**，但结构的最终根据是「the universal laws which make up the unconscious activity of the mind」（PDF p.24）——仍在文化之外，故仍是前转向。 | **格 D：White**。两条原则：意义是符号元素在「相似与差异的网络」中的关系系统（PDF p.31）；两个制度子域以**有序二元性（ordered duality）**共构（PDF p.31–32）。技术上落在块模型、伽罗瓦格、对应分析。**意义就在关系构型本身，模型即读法**；作者称此为**结构性解释学（structuralist hermeneuticists）**（PDF p.29）。 |

**四格各有自己的效度标准，跨格互评是范畴错误**：A 格靠可复制性＋跨域同构（Kroeber 用法剧、荷兰画派也有同样兴衰曲线来论证不是偶然，PDF p.15）；B 格靠解释力（能否解出一个原本无解的对立）；C 格靠增量效度（ΔR²）与面效度；D 格靠结构稳定性＋与史料细节的吻合（Mohr & Neely 用「四重合法性领域 + 一个亲缘结构残迹」论证模型读出了历史层积，PDF p.34–35）。**用 C 格的 R² 去否定 D 格，或用 D 格的「多义」去否定 C 格，都是错位比较。**

**两个补充装置**：
- **四种知识功能（four knowledge functions）**：representation（把复杂压成可测的简单，代价是「a necessary brutalization of reality」，PDF p.5）、heuristic（把零散信息聚成格式塔，PDF p.6）、power（把思想外化为物质痕迹，即 Ricoeur 意义上的二阶外化，PDF p.6）、sociality（使分工与协作成为可能，PDF p.7）。（早前批次曾把第四项标为「未核实」，此处已核到为 sociality。）
- **形式模型（formal model）** 的窄定义：「a model must include the study of empirical (collected) data, analyzed with quantitative or other formal pattern analysis procedures so as to obtain a structure-preserving reduction into a simpler, more easily describable set of features or characteristics」（PDF p.2）。约简之所以不是任意压缩，是因为必须保住原系统中被理论认为重要的关系结构——**保结构同态（structure-preserving mapping / homomorphism）**（PDF p.4）。这一定义把「纯思辨的抽象模型」与「只做细读」都排除在外：计算＝**有数据、有保结构约简的分析**，不是「用了电脑」。

**今天该站在哪个战场**：作者画了两支箭头——文化转向时代的主战场是「后转向质性 vs 前转向量化」（箭头 3），今天的主战场是「后转向质性 vs 后转向量化」（箭头 5）（PDF p.12）。这意味着本路线的对手不是「老式量化」，而是「已经承认文化构成性的质性研究」；争论的焦点不是「能不能量化」，而是「量化能不能读出意义」。

### 2.3 勘误：不存在「四条路径」的统一说法

**混淆一：把「四条路径」记成 Mohr et al. (2020) 的框架。**
- 2020 年的书**没有**「四条路径」这一分类。全书骨架是**三个层次**（人／物／关系）＋**一对张力**（解释／测量）＋**一个过程概念**（pivots）。全书检索无「four ways」「four paths」之类提法；p.78 出现的「four ways」指的是**物件章**里物件关系测量的四个子类（对象间关系、解释对后续对象生产的影响、物件在人群中的扩散、物件用于传播观念与标识类别）。
- 「Four Ways to Measure Culture」是**另一篇文献**：Mohr & Rawlings (2010)，为 Alexander/Jacobs/Smith 编 *The Oxford Handbook of Cultural Sociology* 所写。它的「四」是**一个 2×2 格**（文化转向前/后 × 是否以解释学为目标），不是「人/物/关系/网络」四条。四格各配一个理想型：Kroeber／Lévi-Strauss／DiMaggio／White（PDF p.16–34）。
- **写作纪律**：要写「四条路径」，必须写成「Mohr & Rawlings (2010) 的 2×2 范式格」；要写 2020 年那本书，必须写成「三层×二重性×枢轴」。**二者不可混用，也不可互相替换页码。**

**混淆二：把本底稿 §3 的六类技术当成「作者的路径分类」。**
§3 的频次／词典／主题模型／词嵌入／关系性方法／品味三模态，是**为使用方便所做的技术—逻辑归类**（判断），每一格都能落到具体页码，但它不是任何一位作者的原始命名。原始命名只有两套：2020 书的「三层」，2010 文的「2×2」。把技术清单说成「Mohr 等人划分的六条路径」，等于把整理者的脚手架当成原文。

**附带一条常被写反的判断**：「文化分析（cultural analytics）是数字人文（digital humanities）的子集」。**原文相反**：Manovich 说 DH 这个词对他「was both too broad and too narrow」——太宽（含数字化、教学、出版），太窄（「digital humanities scholars were working almost exclusively with datasets of historical literary texts as opposed to other types of media or contemporary digital culture」，PDF p.20）；他还明确拒绝给领域划界：「The goal of this book is not to draw a boundary around the field... Cultural analytics for me is the instrument to question all categorical boundaries」（PDF p.27），并说这本书是「a book of media theory」（PDF p.31）。三者是**功能分工**（阐释／说明／自动化，PDF p.169），不是领土包含关系。

---

## 3. 技术谱系（每种：原理直觉 → 输入 → 关键参数 → 输出 → 怎么读出文化含义 → 效度威胁）

> 读这一节的顺序：先看你手上的材料落在哪一格（§2.1 的三层），再看这个技术的**输出单位**是不是你理论里那个单位。单位不对，参数调得再好也没用。

### 3.1 频次/分布（词频、tf-idf）

**原理直觉**：文化最容易被看见的一面是**注意力份额**——谁被谈得多、哪些词在涨。词频是「某词在某文档中出现次数／该文档总词数」（Silge & Robinson 2017, PDF p.47）；tf-idf 是词频乘逆文档频率，`idf = ln(ndocuments / ndocuments containing term)`（PDF p.45–46），它找的是**区分性**而非频率（Siddiqui 2025, PDF p.168）。背景结构是**齐夫定律（Zipf's law）**：「the frequency that a word appears is inversely proportional to its rank」（Silge, PDF p.48）——这条定律解释了为什么高频词几乎没有信息。

**输入**：时间戳可靠、来源可核查、体裁相对稳定的语料；一套稳定的类目或词典。

**关键参数**：`min_df`／`max_df`（剪词表）；是否 `sublinear_tf`；参照语料（idf 依赖它）；时间切片粒度。

**输出**：词×文档矩阵；按 tf-idf 排序的词表；议题份额的时间序列。

**怎么读出文化含义**：读**份额的变化**与**排他词**，不读绝对频次。必须先做一次「未清洗 vs 清洗后」的对照——景永霞等的实验最硬：搜狐新闻「2008」类 20 篇文档，未删特殊符号、未去停用词时，词频前 10「只有 3 个词是有意义的」，过滤后「每个词都基本和主题『奥运会』相关」（PDF p.105–106）。这一段可以直接搬进方法节，用来论证「为什么要清洗」。

**效度威胁**：**语料建构会伪装成文本内部的模式**。Google Books N-gram「认知扭曲上升」的经典案例：2020 版语料中虚构类比例大增，研究者可能只是在测「虚构类占比上升」（Stoltz & Taylor 2024, PDF p.28–29）。作者的判词：「Size does not guarantee a fair sample; rather, it may increase one's confidence while reducing one's ability to manually validate conclusions.」（PDF p.29）第二重威胁是 tf-idf 本身不稳健——作者自陈「The statistic tf-idf is a rule of thumb or heuristic quantity… its theoretical foundations are considered less than firm by information theory experts.」（Silge, PDF p.45）。第三重是跨期可比性：语料规模变化会系统性改变 idf（判断，由 p.45–46 的公式推出）。第四重：tf-idf 最高值常常是人名（Siddiqui, PDF p.158），做文化分析前必须先做词性/实体过滤。

### 3.2 词典与人工编码

**原理直觉**：把「什么算某种意义」写死成一张表，然后数。词典法的加总逻辑被作者摊在桌面上：「Dictionary-based methods… find the total sentiment of a piece of text by adding up the individual sentiment scores for each word in the text.」（Silge, PDF p.30）——**意义可加、语境不计**，这就是它全部的力量与全部的脆弱。

**输入**：公开可查的词典（AFINN／Bing／NRC，PDF p.28；中文常用知网、百度、哈工大三表，景 PDF p.105），或一份带定义、正例、边界案例、反例的编码本（Grimmer et al. 2022, PDF p.190–192）。

**关键参数**：词典版本；否定词窗口（前 1–3 词）；程度副词分级；文本块大小；编码员的信度指标。

**输出**：文档层分数或类别；类目计数；编码本＋信度报告。

**怎么读出文化含义**：读**趋势**，不读绝对值。Siddiqui 的判词：「it should be considered a rudimentary gauge of the collective emotional undertones in a text, rather than a precise or nuanced understanding」（PDF p.161），明确失效点是「negations or sarcasm」。中文侧最清楚的反例：「这个手机我喜欢」vs「这个手机我不怎么喜欢」，情感词相同、极性相反（景 PDF p.279–280）。做对这一层的正解在 Müller & Guido 的 n-gram 实验里有系数级证据：IMDb 情感分类用 `ngram_range=(1,3)` 后交叉验证精度从约 0.90 升到 0.91，而真正有信息量的不是单词 `worth`，是二元组「not worth」（负面）与「definitely worth」「well worth」（正面）（PDF p.282–284）。

**效度威胁**：① **语境不计**——「these methods do not take into account qualifiers before a word, such as in 'no good' or 'not true'」（Silge, PDF p.30）；② **文本块大小改变结论**——「A text the size of many paragraphs can often have positive and negative sentiment averaging out to about zero, while sentence-sized or paragraph-sized text often works better.」（同页）；③ **适用范围**——「we may hesitate to apply these sentiment lexicons to styles of text dramatically different from what they were validated on」（同页）；④ **词典的领域性与不可扩展性**——「同一词汇在不同的词典中可能表现出不同的极性……且这类方法具有领域性，可扩展性差」（景 PDF p.279）；⑤ **只靠极端值造假精度**——Goertz 的「灰区（gray zone）」警告（Grimmer, PDF p.342–343）。

### 3.3 主题模型（LDA / STM / coherence）

**原理直觉**：文档是主题的混合，主题是词的混合（Silge, PDF p.104）。技术上它是**降维**：Stoltz & Taylor 说得最准——「They all share a focus on uncovering the latent themes of a corpus. These are all dimension reduction methods, where the goal is to find the major axes of variation, or dimensions, along which word co-occurrences are organized.」（PDF p.201）。**这句话把主题模型从「发现真实类别」降格为「找方差主轴」**，是抵抗「K 就是世上真有 K 个主题」的第一道防线。

**输入**：足够长、足够多的文档＋文档层元数据（时间、来源、作者）。原文量级：TREC AP 新闻 16,000 篇（Blei et al. 2003, PDF p.15）；困惑度实验另用两个万篇级语料（同书 p.16 一带，未逐页核）。

**关键参数**：**K**（无解，见下）；α（文档—主题先验，小 α 使文档稀疏，PDF p.13–14）；初值（原文用 5 篇文档播种以避免所有主题塌成一个，PDF p.16；STM 用 50 个初值各估一次、按下界剔除剩 10 个，Roberts et al. 2014, PDF p.10）；STM 的 X（prevalence 协变量）与 U（content 协变量）（PDF p.4）；正则化强度（PDF p.6）。

**输出**：β（主题×词概率）与 θ／γ（文档×主题比例）（Silge, PDF p.106；Siddiqui, PDF p.173–174）；STM 另给 prevalence 效应与 content 效应（PDF p.4）。coherence 给每个主题一个负值（Mimno et al. 2011, PDF p.4）。

**怎么读出文化含义**：四步，缺一不可。
1. **读排他词，不读高频词**。原文只用最高概率词，会导致所有主题都由 the/year/new 主导（Blei, PDF p.17）；替代品是 FREX（frequency-exclusivity，Roberts, PDF p.5）。
2. **读 θ 的分布形状**。全部接近均匀 → K 太大或语料没有主题结构；每篇接近 one-hot → K 太小（判断，据 Blei PDF p.5 的混合隶属设定）。
3. **读 exemplar 原文**。Stoltz & Taylor 的纪律：「We should never just rely on the list of top terms for assigning meanings to the topics. We need to read the texts.」（PDF p.205）原文示范也是取某主题 θ 最高的几篇通读（Blei, PDF p.15）。
4. **分清「谈多少」与「怎么谈」**。STM 的最大概念贡献是 prevalence（θ，协变量经 LogisticNormal(Xγ, Σ) 进入）与 content（κ，β_k ∝ exp(m + κ_k)）的分离（Roberts, PDF p.4）。二者可以背离：处理组可能没有多谈移民，但把移民从「法律／边境」改说成「工作／家庭」——**只看 prevalence 会漏掉框架变化，而框架变化往往才是文化效应**（判断，据 p.4 与 p.10 的交互例）。

**效度威胁**：
- **K 没有正确答案，只有纪律**。LDA 原文：「the dimensionality k… is assumed known and fixed」（PDF p.4），全文唯一标准是 held-out 困惑度（PDF p.16）。STM 说得更直白：「There is no 'right' answer to this choice. Varying the number of topics varies the level of granularity of the view into the data.」（PDF p.6）并明确反对用边际似然选模型：「that maximizes model fit and not substantive interpretation」（同页）。Mimno 则证明 K 越大，最小的主题越差，「as many as 10% of topics may be so bad that they cannot be shown without reducing users' confidence」（PDF p.1）。**任何声称「用困惑度确定了最优 K」的论文，都在做 STM 明确反对的事。**
- **困惑度与人类判断会背离**。Stoltz & Taylor 的直接记录：「This is an example of where a statistical criterion does not always agree with the eye test.」（PDF p.205，指 LSA 建议的 K 与可解释性不一致）。
- **coherence 是语言习惯的指标，不是文化重要性的指标**。得分最高的主题往往是套话（基金摘要里的「培训项目」），真正有张力的主题得分低（Mimno, PDF p.4–5）；且它对主题大小高度敏感，小主题天生低分（同页）。正确用法是**诊断缺陷类型**：Chained（桥词连起两个概念）、Intruded（两套话语强行拼接）、Random、Unbalanced（抽象层次混杂）（PDF p.3）——**把缺陷类型当发现，而不是当错误**。
- **词袋会拆散固定表述**。原文自证：`William Randolph Hearst Foundation` 会被分到不同主题（Blei, PDF p.15）。Siddiqui 的比喻更狠：「the sentence 'the dog ran outside,' with its clear subject-verb order, is rendered indistinguishable from a jumbled 'outside the ran dog.'」（PDF p.147）
- **短文档不稳**。coherence 的共现单位是**文档**，不是句子或窗口（Mimno, PDF p.4）；推文、开放题这类短文本共现稀疏、整体偏低（判断，由该设定推出）。

### 3.4 词嵌入与语义几何（共现→PPMI→SVD、维度轴、对齐）

**原理直觉**：一个词的意义由它的邻居决定（Firth：「You shall know a word by the company it keeps」，Stoltz & Taylor, PDF p.24 引）。技术上四步：共现矩阵（TCM）→ PMI/PPMI 加权 → 降维（SVD 或 GloVe/word2vec）→ 词向量。**关键补充**：嵌入能捕捉「不共现也相近」——「words need not literally co-occur to be close. Even if 'pie' and 'cake' never co-occur, they do share context words like 'sweet,' and 'fruit.'」（Stoltz & Taylor, PDF p.245 边注）。这既是力量，也是「意义=分布」这一强假设的来源。

**输入**：大规模、跨时间、题材混杂的文本。门槛：类比测试要可靠，「输入至少需数百万词」（Kozlowski et al. 2019, PDF p.25，引 Hill et al. 2014）；历时研究经验下界约每期 ≥10^7 词（判断，据 Hamilton et al. 2016, PDF p.5 对 SGNS 在小语料上检测力不足的说明）。

**关键参数**：
- **维度**：300（Kozlowski, PDF p.14，依据 Mikolov 等在类比任务上的发现；作者另说「substantial natural language corpora require k ≥ 300」，PDF p.6）。Stoltz & Taylor 的说法是「Somewhere between 100 and 300 dimensions is optimal for representing words」（PDF p.232）。
- **窗口**：Hamilton 用对称窗宽 4（每侧），依据 Levy 等推荐＋预备实验调参（PDF p.3）；宽窗对句法不敏感、对语义更敏感，但只能减轻、不能消除句法效应（Boutyline & Arseniev-Koehler 2025, PDF p.5–6）。
- **最低词频**：每十年 ≥25 次（Kozlowski, PDF p.14）。
- **反义词对数量**：10 对与 40 对结果差异不大，但对数越少越不稳；配错（rich−poor vs rich−impoverished）影响很小（Kozlowski, PDF p.15）。
- **轴的两端**：必须**只在所关心的关系上不同**——词性、数、语域要匹配（Boutyline & Arseniev-Koehler, PDF p.12）。
- **对齐**：跨期必须先做**正交 Procrustes 对齐（orthogonal Procrustes）**，求正交矩阵 R(t) 使 W(t)Q 与 W(t+1) 的 Frobenius 距离最小，解由 SVD 给出（Hamilton, PDF p.4）。

**输出**：三层。(1) 一个 N×300 矩阵；(2) 一张「词×文化维度」的投影表（因向量已归一化，投影值等于余弦相似度，Kozlowski, PDF p.9）；(3) 一张「维度×维度」的夹角矩阵，可跨期比较（同页）。历时研究另加「词×十年」的位移量表与成对相似度时间序列（Hamilton, PDF p.4）。

**怎么读出文化含义**（四步，每一步都有坑）：
1. **先验轴的两端是不是真的同一件事的两极**。只取真反义对，并检查两端词在语料中是否都常见；若「富」端全是名词、「穷」端全是形容词，轴就混入词性效应（Kozlowski, PDF p.8–9；Boutyline & Arseniev-Koehler, PDF p.12 把这条写成硬要求）。
2. **读极端词，不读中间词**。看某维度投影最高与最低的各 10 个词。Kozlowski 的例子极漂亮：1900 年代富裕维度最高词里有「fragrance / perfume / jewels / gems」，全部强女性化——由此读出「上层女性是展示财富的文化模特」（PDF p.19）。
3. **读夹角，不读单点**。单点投影会漂（相邻十年 >.9，1900 与 1990 之间降到 .6–.7，PDF p.21–22），夹角稳定；夹角才是「文化结构」。全文唯一的结构性变化是教育与富裕的靠拢（PDF p.19–20）。
4. **回到原文找例句**。作者遇到怪结果（「patient」「expectancy」在雇佣维度负端）时明确警告这是「post hoc interpretivism」的陷阱，「vulnerable to misleading conclusions drawn from statistical flukes」（PDF p.22）。另一条更细：读**反向证据**——「boy」在 80 年间与「intelligence」越来越近，看似刻板印象加深，但「boy」与「unintelligence」也同样变近，真相是「男孩越来越被以智力来评价」（Boutyline & Arseniev-Koehler, PDF p.14）。**这一步不做，几乎必然误读。**

**效度威胁**：
- **轴是研究者指定的，不是算法发现的**。Kozlowski 的轴＝反义词对向量差的平均（PDF p.8–9、p.14 公式）；换一套词表，轴就变。稳健性检验只证明「对数多少不太要紧」，没有证明「词表选择不要紧」（判断，据 PDF p.15）。
- **上下文空间 ≠ 概念空间**。Boutyline & Arseniev-Koehler 的核心区分：嵌入直接估计的是**上下文空间（context space）**——「Abstract many-dimensional space that summarizes the tendency of terms to be used together with other terms」；社会学家想要的是**概念空间（concept space）**——「represents concepts in terms of their semantically meaningful features (like their size, status, or gender)」（Table 1，PDF p.9）。两者的桥叫**同构（isomorphism）**：上下文空间 C 是概念空间 F 的有效代理，当且仅当「the relative proximity between concepts in F equals that between the corresponding words in C」（同页）。**桥不是必然的，是要一座座搭的。**
- **非语义关联（nonsemantic association）**：拼写（colour/honour）、OCR 错误、固定搭配（French fries）、专名大小写、新闻电头格式（「CHICAGO, June 10」让月份与城市靠近）造成的邻近（PDF p.6）。判词：「An association thus does not become semantic simply by being common and strong.」（PDF p.7）
- **强式分布假设近乎同义反复**。「By offering no definition of meaning beyond the assertion that it is captured by words' distributions across contexts, the strong form of the hypothesis flirts with tautology… it sweeps the question of meaning under the rug.」（PDF p.5）
- **跨域比较不合法**。「Yesterday」没有性别、颜色、重量；「dollar」没有速度；「squirrel」没有宗教与收入（PDF p.10）。两个概念可能没有任何共同特征维度，此时它们的余弦相似度只是非语义规律的产物——由此推论，像 Concept Mover's Distance 那样把文档中所有词与一个目标概念比较，可能主要在比较表面形式（PDF p.12–13）。
- **LLM 不是解药**。作者自做实验：从 BERT-base 取静态嵌入层，构造「不定式 vs 现在分词」「比较级 vs 原级」「副词 vs 形容词」「英式 vs 美式拼写」等纯形式轴，投影数百对词，**每一类关系的正确侧向率都 >90%，多数 >99.5%**（PDF p.14–15）。
- **历时比较不对齐＝把旋转当变化**。SVD 与 SGNS 都会产生任意正交变换，年内余弦相似度不受影响，跨年就全乱（Hamilton, PDF p.4）。
- **语料 artifact 会产生假发现，而且可诊断**：`special`、`cover`、`romance` 是书籍封面广告造成的；`male` 不是意义变了，而是性别平等话语让它出现在新语境里（Hamilton, PDF p.5，Table 4 注）。
- **投影是语料层的量，不是任何个人的态度**（Kozlowski, PDF p.2）。

### 3.5 关系性方法（二模网络、块模型、对应分析、RULeNet、微类型）

**原理直觉**：意义在关系里，不在取值里。这一支与词嵌入的分野是「什么算关系」——嵌入用**共现**（同一上下文窗口一起出现），关系性方法用**选择／使用／蕴含**（同一个人选了它，或一条规则把它连到另一个）（判断，综合 Mohr & Rawlings PDF p.31–34、Lizardo 2024 PDF p.1–5、Gondal 2025 PDF p.3）。

**输入**：人×项目的二值矩阵即可——「all data, whether collected purposefully as 'network' data or collected as part of a traditional social survey, is relational data」（Lizardo 2024, PDF p.1）。这把网络分析工具箱合法地搬到了问卷上。

**四种典型技术与关键参数**：
- **结构等价与块模型（blockmodel）**：把「在关系模式中占据相同位置」的行动者／词聚成一类。Mohr & Rawlings 用 1888 年纽约慈善名录的 168 所监禁机构文本，把身份词按使用模式分块（PDF p.33–34）。这一步把「同义」操作化为「结构等价」——两个词意义相同，不是因为定义相同，而是因为它们在话语里占同一个位置。
- **对应分析（correspondence analysis）／几何数据分析**：场域测量＝找该场域特有的资本种类及其分布（Mohr et al. 2020, PDF p.113），主流技术就是对应分析（PDF p.116）。Manovich 也指出 *Distinction* 的技术核心正是 correspondence analysis（PDF p.133–134、p.294–295）。
- **链接聚类／微类型（link clustering / microgenre）**：把「人—品味」的**连线**而非人或品味当作聚类对象；两条共享同一品味的连线，其相似度＝两个人文化自我网络的 Jaccard 系数（Lizardo, PDF p.5，式 1）；切点 C 决定得到几个微类型，微类型严格嵌套于大类型之内（PDF p.7）。作者的量级：2,263 人 × 20 项 = 9,216 条边（PDF p.4）。
- **RULeNet／关联规则（association rules）**：形如 U→V 的蕴含，来自零售购物篮分析（Gondal, PDF p.3–4）。三参数：支持度（support，同时满足前后项的比例）、置信度（confidence，前项成立时后项成立的比例）、提升度（lift，confidence ÷ support(后项)）；作者用 (0.02, 0.8) 与 lift ≥ 3（PDF p.4–5）。作者量级：SPPA 2017，15 个文化活动，8,523 个完整个案（PDF p.6）。

**输出**：相似度矩阵／谱系树／微类型归属表（Lizardo, PDF p.7）；规则表＋有向网络图＋子样本图（Gondal, PDF p.6）；对应分析的行动者—资本双标图与前两轴（Mohr, PDF p.116）。

**怎么读出文化含义**：
- **微类型要当因变量做回归，看它是否推翻大类型的结论**。Lizardo 的说服力全在这一步：大类型看，Metal 爱好者是低教育、白人、男性、年轻，完全符合 Bryson 的经典图像；切成三个微类型后，第一个微类型的教育梯度是平的（p=.54），且父母有大学学历者更可能选择它（p<.05），种族与性别中性（PDF p.9）。Salsa 亦然：大类型层面与教育无关（p=.26），第二个微类型显著偏向高教育、父母高教育、且年龄更大（PDF p.11）。
- **看后项的入边集中度 → 谁是「统一者」；看一个节点的出边分散度 → 谁是「分化者」**（Gondal, PDF p.3–4）。SPPA 里 ART（参观美术馆）是 109 条规则的后项，是最强的统一者；而最常被选的 NOVELS（读小说）**不在中心**，因为以它为后项的规则 lift 都低于 3——**最流行 ≠ 最统一**（PDF p.6）。这是全文最漂亮的一个发现。
- **看同一个前项指向多个后项 → 多义**。重金属恨者同时指向「爱古典」与「恨古典」，区分器是「对歌剧的态度」；作者由此论证：一个不常见的偏好（爱歌剧）可以充当边界条件（PDF p.3、p.11）。
- **看互惠边比例 → 整体是共同体式还是层级式**。SPPA 里多数边非互惠，这本身就是一个关于文化分层结构的论断（判断，据 PDF p.6 的描述）。
- **RCA 的读法**：一个歌剧恨者/说唱爱好者与一个歌剧爱好者/说唱恨者，距离为 0，因为他们共享同一个「高雅 vs 商业」的区分图式（Mohr et al. 2020, PDF p.39–40）。**这是「意义在关系里而不在取值里」最干净的操作化。**

**效度威胁**：
- **网络边界随手定**（Mohr, PDF p.148–149）；把结构等价当因果；忽略「场域之间」的空间（Eyal 语，PDF p.149）。
- **二值化规则实质决定结果**。Lizardo 用「喜欢 **且** 经常听」才算 1（PDF p.4）；若只用「喜欢」，会纳入大量弱偏好，边密度上升、微类型变模糊（判断，据其说明）。这是最该做敏感性检验的参数。
- **切点是研究者选的**。作者诚实承认「fix k and choose a C」是允许的操作（PDF p.7），所以「发现了 3 个微类型」应写成「在 3 个微类型的粒度上，发现……」。
- **没有稳定性检验**。Lizardo 未做交叉验证或 bootstrap 重抽样看微类型是否稳定（判断，据 PDF p.8–11 的效度说明）；两个案例还是按「文献中已有微类型假设」挑的（PDF p.7）。
- **RULeNet 没有整体拟合指标**。「there are no goodness of fit criteria that can be applied to the full model」（Gondal, PDF p.11）；三个阈值靠惯例（「choice of various criteria... is also based on convention rather than fit」，PDF p.12）；横断面的方向是**推断**的（PDF p.3）。
- **对应分析的二维平面可能过度约简**。Kozlowski 用几何论证：若把三维结构压到二维，无法同时保住 90°、85.5°、79.3° 三个夹角（PDF p.21，Fig. 8）。这是对「布迪厄式二维社会空间」最硬的一次技术批评。

### 3.6 品味的三模态与「伪项目」测量

这两项不是算法，是**测量之前的那一步**——先把「我要测的是哪一面」定清楚，否则后面所有技术都在测错的东西。

**三模态（three paradigms）**（Ma Xiangyu 2024）：
- **偏好范式（preference paradigm）**：品味＝对文化对象的情感反应（「你最喜欢哪个音乐人？」）。
- **消费范式（consumption paradigm）**：品味＝实际参与／消费（「你听得最多的是谁？」）。
- **评价范式（valuation paradigm）**：品味＝对文化对象的社会评价能力（「谁的音乐最好？」）（PDF p.4）。
作者的方法是**回溯推理（retroduction）**：从测量实践反推概念预设（PDF p.3）。主张是**厚主体性（thick subjectivity）**——品味是「a kind of orientation ('subjectivity'), expressed through multiple modalities of action ('thick'), that describes how we feel, consume, and praise in cultural fields」（PDF p.9）。三模态一致的叫**简单品味**，存在**反义（antinomy）** 的叫**复杂品味**；组合数 2³−1=7，故复杂品味有 6 类：罪恶快感、习得前品味、品味姿态、有距离的消费、有理由的弃绝、遥远的赞赏（PDF p.12–16，Table 1）。判词：「an omission of the antinomy between its taste modalities denies a complex taste the nature of its being.」（PDF p.12）
**怎么用**：① 先判定手上的指标属于哪一模态再解释数值——用「过去 12 个月是否去过美术馆」测「品味」，测到的是消费，不是偏好（据 PDF p.4 的提问方式判据）；② 三模态不一致时**不要当测量误差，要当类型**；③ 用民间概念（装腔、恨看、附庸风雅）做锚，检验类型学是否覆盖真实生活（PDF p.12–16）。
**效度**：概念效度，不是统计效度；三条论证是回溯推理的合法性、三义的互补性、与民间概念的对应（PDF p.3、p.9–10、p.12–16）。

**伪项目（pseudo items）**（Childress 2025）：
- **原理直觉**：在问卷里塞进五个**不存在的人**，看谁说自己认识——用「不可能知道的东西」分离「知道」与「表现得知道」。
- **输入**：一份含真项目与伪项目的问卷；5 个左右伪项目；1,000–2,000 人（作者 1,900，Prolific 配额样本，PDF p.6）。**必须显式提供「我不知道这个人」选项**（PDF p.6 的培训模块）。
- **关键参数**：伪项目命名要「non-systematically with an eye towards breadth」——按性别、族裔／国别、时代感分布（PDF p.6）；位置随机嵌入真偶像列表（同页）；模型用 Poisson（计数 0–5），辅以二值 logit（同页）。
- **输出**：系数表（负号＝更少说「不知道」＝更多声称知道）；按伪项目分拆的系数图；三种理论预测方向 vs 实际结果的对照表（PDF p.5、p.9）。
- **怎么读**：① 读**伪项目知晓率与真人知晓率的对比**，不读绝对值——7–13% 本身没有意义，有意义的是它**不低于** Mary Anning（10%）与 Juliette Gordon Low（15%）（PDF p.6）；② 读「哪些变量预测声称知道」，因为没人真的知道，所以任何显著正效应都只能解释为**倾向**，不能解释为知识；③ 读「教育的零效应」当**交叉压力**的证据（教育同时提升「觉得自己有权说」与「辨别真伪的能力」，PDF p.8），而不是当「教育无关」（PDF p.7）。
- **效度**：四重——与既有伪项目研究的比率一致；与真人基准对比；稳健性（加入培训需第二次机会等变量后结果不变）；**理论上的可证伪性**（三种框架给出方向相反的预测，PDF p.5、p.9）。
- **关键系数**：童年艺术接触 +5%／单位、网络多样性 +18%、商科专业 +22% 显著增加「声称知道」；男性比女性边际效应约 +17%（PDF p.7）。

---

## 4. 验证：什么算证明了你的测量

**总纲**：这条路线的验证不能靠模型拟合诊断。「These validations often involve careful reading of the documents, codebooks with category definitions, and/or application-specific criteria, rather than model-fitting diagnostics」（Grimmer et al. 2022, PDF p.50）。原因是它采取**不可知论立场（agnostic approach）**：「there are no 'true' values for us to target with text-as-data methods, or no one best model」（PDF p.49）——**正因没有真值，验证才是唯一的合法性来源**。

### 4.1 Grimmer 的测量五原则（PDF p.278–280）

| 原则 | 具体怎么做 | 常见糊弄法 |
|---|---|---|
| **1. 明确目标** | 写清这项测量要服务哪个推断；承认「measurement is a reduction，没有普遍对错，但有清楚的范围与用途」 | 用「我们测了文化」代替「我们测的是某年某平台某类行动者的 X」；把测量当描述，又拿它做因果结论 |
| **2. 标明原材料** | 公开语料来源、抽样框、时间窗、体量；最好公开语料或至少公开检索式 | 只写「爬取了微博数据」；不写关键词、不写删帖造成的断点、不写每条的平均长度 |
| **3. 编码过程可解释、可复现** | 「a measurement cannot properly be a part of science if we don't know how it was generated」（PDF p.279）；据此**拒绝黑箱式现成测量** | 直接调用某个商用情感 API 或某个预训练模型打分，不报告版本、训练语料、阈值 |
| **4. 测量必须被验证** | 「Validation is the process of establishing to readers and the researchers themselves that the measurement maps well to the theoretical concept that it purports to measure.」（PDF p.279） | 只报内部指标（困惑度、轮廓系数、训练集准确率）；把「模型收敛」当「测量有效」 |
| **5. 局限必须被探查、记录并告知** | 逐条写误差来源，包括「不同群体误差率不同」的公平性含义（PDF p.280） | 把局限写成「样本量有限，未来可扩大样本」这类不触及效度的话 |

配套的**六原则**（PDF p.55，Table 2.1）：① 实质理论与知识对研究设计不可或缺；② 文本分析不替代人，而是**增强**人；③ 理论建构需要迭代与累积；④ 方法从语言中提炼概括；⑤ 最好的方法取决于**任务**；⑥ 验证不可或缺，且方式取决于理论与任务。第 ⑤ 条是全书的方法论签名：「We will treat the same statistical model very differently in the context of discovery than in measurement because the task is distinct.」（PDF p.48）

### 4.2 四种「无金标准」验证（PDF p.342–343）

金标准的定义先要立住：「labels are correctly coded and perfectly reflect the concept of interest」（PDF p.338）。有金标准时用混淆矩阵＋与任务匹配的指标——注意社会科学常是「characterize the haystack」，此时文档层 accuracy 不如**比例估计的偏差**重要（PDF p.339）。

| 验证 | 具体怎么做 | 常见糊弄法 |
|---|---|---|
| **替代标签（surrogate labels）** | 找一个与目标概念理论相关、但可独立测量的变量（收敛效度）；报告相关系数并说明为何不是同义反复 | 用一个同样有争议的测量当「真值」；相关系数低就说「文化是隐蔽的」 |
| **部分类别复现** | 只检验你能确证的几个类别（如明确的正例／反例），报告命中与漏判 | 只报命中的类别，不报漏判；把「没检验的类别」写成「模型已覆盖」 |
| **非专家人类评估** | 抽 20–30 条盲评；主题模型用**入侵者检测（intruder detection）**：给评估者看某主题的 4 个词，其中 1 个来自别的主题，问哪个不属于（Chang et al. 2009，转引 PDF p.342–343） | 让作者自己评；让评估者看到主题编号与命名；样本只取最清楚的几条 |
| **与外部信息对应** | 与事件史、制度变动、独立统计（如发行量、票房、法案数）对齐；报告时间上的同步与滞后 | 只挑对得上的时点讲；把任何同步都读成因果 |

**一条硬警告**：只靠极端值也能做出相关系数 0.5 的假精度——Goertz 的「灰区（gray zone）」问题（PDF p.342–343）。所以样本必须包含**边界案例**，不能只取两端。

### 4.3 FPCILV：用文本做因果最致命的一坑

**定义**：「occurs when the analyst creates dependence between units by developing the mapping function with reference to the outcome of treatment in the experiment」（PDF p.416–417），从而违反 SUTVA。翻成操作语言：**你先看了处理组的结果，再据此造测量，单位之间就不再独立。**

**正解**（PDF p.417–418）：**顺序科学（sequential science）**——在实验内部切样本，训练集用来发现／校准映射函数（mapping function），测试集用来估效应；映射函数在进入推断前必须**固定**（PDF p.418）。配套说法：「Nothing about using text data absolves us from the core challenges with causal inference.」（PDF p.416）

**糊弄法**：全样本跑一遍 LDA 得到主题，发现「处理组更常谈某个主题」，然后把这个主题比例当因变量回归处理变量——映射函数与处理结果互相依赖，估计量已经不可解释。

### 4.4 四类可复用的效度模板（跨文献）

| 模板 | 怎么做 | 范例与页码 | 适用格位 |
|---|---|---|---|
| **与人类评分相关** | 小规模调查／众包评分（30–50 人即可起步），与测量值求相关 | Kozlowski：398 人 MTurk、59 词、7 个领域，阶级 .53／性别 .76／种族 .27（PDF p.16）；1958 年语义差异量表 349 词×20 维，6 维 >.60（PDF p.13、p.16–17） | C 格（造指标） |
| **与既有质性研究吻合** | 先用文献里的亚文化假设，再看聚类是否复现 | Lizardo：Metal 微类型对应 Tampubolon 与 Goldberg，Salsa 微类型对应 Bachmayer 等的质性等级（PDF p.8–11） | D 格（读结构） |
| **与人工编码对比** | 同一批材料双轨编码，比聚合计数、逐条归类、类别数 | Roberts：ANES 开放题，STM 60 主题 vs 人编码 69 类，94% 的回答在「涉及几个类别」上相同或只差一个（PDF p.16） | C 格 |
| **可证伪的方向性预测** | 让竞争理论给出**方向相反**的预测，看哪一方胜 | Childress：过路知识 vs 倾向性开放对「谁会声称知道伪项目」给出反向预测（PDF p.5、p.9） | 任意格，最强 |

**跨格警示**：四类模板不能互换。用「与人类评分相关」去要求一个 D 格研究，等于要求它交 C 格的作业（§2.2）。**同一篇论文里若混用两格的标准，审稿人会先问「你到底在哪一格」。**

---

## 5. 可执行流程（12 步 checklist）

> 每步一句说明＋一句成败判据。判据不通过就不要进下一步——这条路线最常见的失败不是算错，而是**在前面几步就已经测错了东西**。

1. **把问题写成三元组**：文化对象（图式／叙事／框架／分类／评价维度）× 分析层次（人／物／关系）× 目标（发现／测量／因果）（Grimmer, PDF p.43–46）。**判据**：三格都能用一句话填满，且不出现「顺便看看」。
2. **划定「局部意义系统」**：谁的语言共同体、什么场景、哪个时间窗、什么体裁；写成 memo 并公开。**判据**：能回答「谁不在这套系统里」——Mohr 的功能等价表述是 in situ（PDF p.66–67）与网络／场域边界（PDF p.148–149）。（注：全书无「local meaning structures」一词，此术语出处**未核实**，勿当原文引。）
3. **语料建构并记录偏倚**：写清 population → sampling frame → 实际语料；逐条核对四类偏倚（资源、激励、媒介、检索，Grimmer, PDF p.43–45）与「文本不是人」的三条理由（Stoltz & Taylor, PDF p.30–31）。**判据**：能报出每一年的文档数、来源分布、平均长度；能指出至少一个系统性缺口。
4. **单位化（unitization）**：决定是文档、段落、句子还是事件，并说明理由（Stoltz & Taylor, PDF p.31）。**判据**：换一个单位重跑，结论的方向不变（或变化可解释）。切块能廉价扩容，也是最容易制造伪模式的一步。
5. **表示与预处理**：分词 → 归一化 → 停用词 → 词形/词干 → DTM 或嵌入；每一步当分析决策记录（含分词器版本、词典版本、停用词表版本）（Stoltz & Taylor, PDF p.256；Silge, PDF p.19–20）。**判据**：「when we engage in 'preprocessing,' the analysis has already started」——每个选择都能说出它对结果的可能影响。
6. **发现（若问题开放）**：聚类／LDA／STM；同时报告 K 的选择依据、方差解释、以及「统计判准 vs 肉眼判准」的冲突（Stoltz & Taylor, PDF p.202–205）。**判据**：并列 3–5 个 K 的结论，而不是只报一套。
7. **概念化并写 codebook**：每个类目写定义＋正例＋边界案例＋反例（Grimmer, PDF p.190–192）。**判据**：两位编码员能在不看彼此的情况下把边界案例归到同一类；「起名」不算概念化。
8. **测量**：词典法或监督分类；训练集分层随机抽样、双编码、算信度；固定映射函数（Grimmer, PDF p.279、p.338）。**判据**：能报出编码员间信度、训练/验证/测试的切分方式、以及基线模型（naive Bayes 或 logistic）的表现。
9. **验证**：有金标准→混淆矩阵＋与任务匹配的指标；无金标准→替代标签／部分类别复现／非专家判别（含 intruder detection）／外部信息对应，**至少叠两种**（Grimmer, PDF p.338–343）。**判据**：至少一条验证是**外部**的（不在模型内部）。
10. **稳健性**：换预处理、换 K、换 seed、换模型；做**模拟零假设（simulating the null）**——「loop through our analysis 10,000 times using different seeds」，看结论是否只是某次随机初始化的产物（Stoltz & Taylor, PDF p.292）。**判据**：能说清「哪一种选择会让结论翻转」。
11. **推断或描述**：把测量值放进研究设计；若做因果，先切样本、先固定映射函数，避免 FPCILV（Grimmer, PDF p.416–418）。**判据**：方法节里有一句「映射函数在测试集上未再改动」。
12. **解释学回归**：回到文本细读，写「文本证据卡」（原句＋页码＋你的读法＋反例）；专门检查**沉默**——应有而未出现的词、未受邀者、未上架的书、被删的帖（Mohr et al. 2020, PDF p.150–151、p.157）。**判据**：论文里至少有一处**你的模型解释不了、但你给出了替代读法**的地方。作者的原话是：「The results produced by an algorithm should never be the end game of research: instead, these results should provoke further interpretive analysis.」（PDF p.157）

---

## 6. 中文文本的十二道关卡

> 总纲：第 1–4 关决定「词表对不对」，第 5–7 关决定「极性对不对」，第 8–12 关决定「结论稳不稳」。**中文文本分析翻车，九成在前四关，而论文里被写的通常是第九关。**（判断，据本表各条依据归纳）

| # | 关卡 | 坑 | 解法 | 依据 |
|---|---|---|---|---|
| 1 | **全角/半角与兼容字符** | 同一个「１２」和「12」在词表里是两个 token，同一实体被拆成多个特征 | 第一步就做 Unicode NFKC 归一＋全角转半角，并把转换规则写进方法节 | 景 p.93–94 |
| 2 | **繁简与异体字** | 繁体语料遇上简体停用词表与情感词典，过滤器整体失灵且不报错 | 用 OpenCC 统一为简体，**但保留原文字段**；跨两岸三地语料必须报告转换方向 | （本批文献未覆盖，通行做法，**未核实**） |
| 3 | **分词粒度与歧义** | 全模式切出大量伪词，精确模式又把专名切错 | 用 jieba 精确模式，禁用全模式；对专名/机构名建自定义词典 | 景 p.96、p.100–101；Müller PDF p.268 注 3（中文无词边界） |
| 4 | **领域词与网络新词** | 新词不在词典，被切成单字或整体 OOV，直接改变词频与情感分 | `load_userdict` 补领域词表；词向量做增量训练；人工抽检新词 | 景 p.101、p.186–189 |
| 5 | **停用词表选择** | 通用表把情感词/否定词一起删掉，或删不干净平台噪声（「转发」「哈哈」） | 先跑**未过滤**词频做对照，再按语料增补；否定词与程度副词进白名单 | 景 p.102、p.105；Siddiqui p.153 |
| 6 | **否定与程度副词** | 「我喜欢」与「我不怎么喜欢」在纯词袋下几乎同分，甚至判反 | 否定词窗口规则（前 1–3 词内翻转极性）＋程度副词分级赋权；n-gram 可部分替代 | 景 p.279–281；Müller PDF p.282–284 |
| 7 | **反讽与隐性评价** | 字面褒义、实际贬义（「真是太好了，又涨价了」）会被稳定判成正向 | 承认词袋法在此失效：人工标注一小批反讽样本做校准，只在**聚合层面**解释，并报告误差区间 | Siddiqui p.161（明确说无法处理 negation/sarcasm）；**中文反讽无本批文献支持，未核实** |
| 8 | **分词质量对下游的决定性** | 分词错一处，情感分、主题词、分类特征全错，且错误不可见 | 固定分词器版本、保存分词中间产物、做「换分词器」稳健性检验（jieba／pkuseg／NLPIR） | 景 p.289（列为第一条缺陷）、p.95 |
| 9 | **高维稀疏与特征选择** | 词表几万维、样本几千条，模型记住训练集 | `min_df`/`max_df` 剪词表；TF-IDF 加权；IG/CHI 做特征选择；模型端加正则 | 景 p.292–293（2300 条评论、6631 维基线，3500 维附近最优）；Müller PDF p.282 |
| 10 | **词向量的可复现性** | 换 seed、换窗口、换语料，近邻词全变，结论随之漂移 | 固定 seed 与 `workers=1`；完整报告 vector_size/window/min_count/sg/语料时间；多语料重复 | 景 p.183–184、p.186–189 |
| 11 | **主题数 k 与无 ground truth** | k 随手定成 10，主题无法验证，命名靠感觉 | 跑 k=5…30 比较主题一致性与可解释性；报告多解；明确写出「主题命名是解释行为」 | Siddiqui p.171–172；Chen et al. p.75 |
| 12 | **训练/测试同分布假设** | 随机切分让同平台、同时段、同话题的文本同时进训练与测试，准确率虚高 | 按**时间**或**平台**切分做 out-of-sample；分层（`strata`）；报混淆矩阵与 P/R/F1 而非单一 accuracy | Chen p.22、p.37；Siddiqui p.277–278 |

**三条必须补的中文专属判断**：
- **「换分词器」应当是标配的稳健性检验**，但国内论文几乎不做；景只给了「影响重大」的定性判断（p.289），**没有给出换分词器导致 F1 变化多少的量化实验**——这是一个可做的中文方法学论文题目（判断）。
- **中文停用词表要「三表合用 + 领域增补 + 平台表」**。知网表偏书面、百度表偏搜索、哈工大表偏通用（景 p.105）；再加一张平台特定表（微博的「转发」「哈哈」「//@」）（判断）。
- **中文没有词干提取／词形还原的对应物**。Müller & Guido 用「Our meeting today was worse than yesterday」示范：Porter 词干提取得到 `wa / wors / meet`，spaCy 词形还原得到 `be / bad / meeting`（PDF p.286）；中文的「标准化」是另一套（繁简、异体、同义词归并、新词归一），而这一套在本批文献中**没有任何一本系统处理**（判断）。

---

## 7. 两套代码骨架

> 说明：以下是把本批文献的流程**串起来**的骨架，不是任何一本书的原文代码；**未在本机实测**（两套都需要自备中文停用词表、用户词典与语料）。每一步在注释里标出来源页码，便于回查；凡文献未明示的参数，标「待定」并说明依据。骨架只到「能跑通流程」为止，不展开库的使用手册。

### 7.1 Python（jieba + sklearn + gensim）

```python
# 计算测量路线 · Python 骨架（中文优先）｜未在本机实测
import re, unicodedata, random
import numpy as np, pandas as pd
SEED = 20261021
random.seed(SEED); np.random.seed(SEED)        # 景 p.183-184；Siddiqui p.171

# 1) 读入：一行一文档，最小字段 doc_id/text/date/source/label
df = pd.read_csv("corpus.csv")
df = df[df.text.str.len() >= 20].copy()        # 景 p.89：删空文本与过短文本

# 2) 清洗：NFKC 归一（全角->半角）＋去标签/URL/@
def clean(s):
    s = unicodedata.normalize("NFKC", s)       # 景 p.93-94
    s = re.sub(r"<[^>]+>|https?://\S+|@\w+", " ", s)
    return re.sub(r"\s+", " ", s).strip()
df["txt"] = df.text.map(clean)

# 3) 分词：精确模式＋用户词典（领域词/新词）
import jieba
jieba.load_userdict("userdict.txt")            # 景 p.100-101
df["toks"] = df.txt.map(lambda s: [w for w in jieba.lcut(s) if w.strip()])
# 稳健性：换 pkuseg 新闻模型重跑，看结论是否翻转（景 p.95）

# 4) 停用词：先看未过滤词频，再删；否定/程度副词进白名单
STOP = set(open("hit_stopwords.txt", encoding="utf-8").read().split())
NEG = {"不","没","没有","无","非","未","别","莫","勿","不太","不怎么"}
DEG = {"很","太","非常","特别","极","更","最","稍","略","有点","超"}
df["toks"] = df.toks.map(lambda ws: [w for w in ws if w in NEG | DEG or w not in STOP])
df["seg"] = df.toks.map(" ".join)
df[["doc_id","seg"]].to_csv("segmented.csv", index=False)   # 存中间产物，供审计

# 5) 向量化：DTM/tf-idf（这一步已是特征选择，Stoltz p.256）
from sklearn.feature_extraction.text import TfidfVectorizer
vec = TfidfVectorizer(tokenizer=str.split, token_pattern=None,
                      min_df=5, max_df=0.5, ngram_range=(1, 1), sublinear_tf=True)
X = vec.fit_transform(df.seg)
print(X.shape, X.nnz / (X.shape[0] * X.shape[1]))          # 报稀疏度

# 6A) 开放问题：主题模型，K 无唯一解 -> 必须并列报告
from sklearn.decomposition import LatentDirichletAllocation
terms = np.array(vec.get_feature_names_out())
for k in (5, 10, 15):                                      # Roberts p.6
    lda = LatentDirichletAllocation(n_components=k, random_state=SEED,
                                    learning_method="batch", max_iter=50).fit(X)
    for i, comp in enumerate(lda.components_):
        print(k, i, " / ".join(terms[np.argsort(comp)[::-1][:10]]))
    # 下一步不可省：取该主题比例最高的 3 篇读原文（Stoltz p.205；Blei p.15）

# 6B) 测量问题：按时间切分 + 基线分类器 + 混淆矩阵
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report
df = df.sort_values("date")                                # 时间切，不随机（Siddiqui p.277-278）
tr, te = train_test_split(df, test_size=0.25, stratify=df.label, random_state=SEED)
clf = LogisticRegression(C=1.0, max_iter=1000, random_state=SEED)
clf.fit(vec.transform(tr.seg), tr.label)
print(classification_report(te.label, clf.predict(vec.transform(te.seg)), digits=3))
# 报 P/R/F1 与「比例估计偏差」，不只 accuracy（Grimmer p.339）

# 7) 语义几何：词向量 -> 轴 -> 投影
from gensim.models import Word2Vec
w2v = Word2Vec(df.toks.tolist(), vector_size=300, window=5, min_count=25,
               sg=1, workers=1, seed=SEED, epochs=10)      # 维度/词频门槛：Kozlowski p.14
def axis(pos, neg):                                        # 轴由研究者指定，非算法发现
    v = np.mean([w2v.wv[p] - w2v.wv[n] for p, n in zip(pos, neg)], axis=0)
    return v / np.linalg.norm(v)                           # Kozlowski p.8-9
u = axis(["富裕","富有","阔绰"], ["贫穷","穷困","拮据"])
print(sorted(w2v.wv.key_to_index, key=lambda w: -w2v.wv[w] @ u)[:20])   # 读极端词
# 跨期比较前必须 Procrustes 对齐（Hamilton p.4；Stoltz p.243），否则测到的是旋转噪声
```

**三个「不许省」**：① 存中间产物（分词结果、词表、参数）——否则不可审计；② 切分按时间或平台，不按随机——否则跨期泛化被高估；③ 报告混淆矩阵与多 K 结果，不只报一个 accuracy。

### 7.2 R（jiebaR + tidytext + stm）

```r
# 计算测量路线 · R 骨架（tidyverse）｜未在本机实测
library(tidyverse); library(tidytext); library(topicmodels); library(broom)
library(jiebaR)

docs <- read_csv("corpus.csv") |> filter(!is.na(text), nchar(text) >= 20)

# 1) 中文必须先分词：unnest_tokens() 依赖词边界，否则整句成一个 token
wk <- worker(user = "userdict.txt")                       # 景 p.100-101
docs <- docs |> mutate(seg = map_chr(text, ~ paste(segment(.x, wk), collapse = " ")))
# 依据：Siddiqui p.146-149（全书英文语料）；Müller PDF p.268 注 3

# 2) tidy text：一 token 一行 -> 去停用词
cn_stop <- tibble(word = read_lines("hit_stopwords.txt"))  # 景 p.105 三表选一
tokens <- docs |> select(doc_id, seg, date, label) |>
  unnest_tokens(word, seg) |> anti_join(cn_stop, by = "word")

tokens |> count(word, sort = TRUE) |> head(20)             # 未过滤/过滤后对照（景 p.105）

# 3) tf-idf（区分性而非频率，Siddiqui p.168）
tfidf <- tokens |> count(doc_id, word) |> bind_tf_idf(word, doc_id, n)

# 4) LDA：随机初始化必须固定 seed（Siddiqui p.171）
dtm <- tokens |> count(doc_id, word) |> cast_dtm(doc_id, word, n)
set.seed(20261021)
lda <- LDA(dtm, k = 10, method = "Gibbs", control = list(seed = 20261021))
lda |> tidy(matrix = "beta") |> group_by(topic) |> slice_max(beta, n = 10) |>
  summarise(terms = paste(term, collapse = " / ")) |> print(n = Inf)
# gamma（文档-主题）可挂回元数据做后续回归（Siddiqui p.173-174）

# 5) STM：把「谈多少」(prevalence) 与「怎么谈」(content) 分开（Roberts p.4）
library(stm)
fit <- stm(dtm, K = 10, prevalence = ~ group + factor(year), data = docs,
           max.em.its = 75, seed = 20261021)
# 报告：prevalence 效应 + content 效应 + FREX 词 + exemplar 原文（Roberts p.5, p.10）
# 多 K 敏感性：K = 5/10/15/20 各估一次，比 coherence（Mimno p.4）与可解释性

# 6) 有监督：分层切分（Siddiqui p.278）
library(tidymodels)
set.seed(20261021)
split <- initial_split(docs, prop = 0.75, strata = label)
# recipe 里 step_tokenize() 默认英文规则，中文要么自写 step，要么走预分词列
```

**中文用 R 的三个坑**：① `unnest_tokens()` 不会替你分词，必须 `jiebaR` 或外部预分词；② `get_stopwords()` 没有中文表，必须外接；③ `step_tokenize()` 默认英文规则，中文要自定义或绕开 recipe 走预分词列（判断，据 Siddiqui PDF p.146–154 的中文缺口）。

---

## 8. 八个可复用的研究模板

> 每项给：问题／数据量／技术／输出／可迁移点／页码。选材标准是「换一个语料、换一个国家仍能做」。

**T1 语义轴投影＋夹角（Kozlowski, Taddy & Evans 2019）**
- 问题：某类对象（阶级）在若干文化维度上的**相对位置**是什么？维度结构一百年是否变过？
- 数据量：Google Ngrams 5-gram（覆盖有史以来出版书籍约 6%），按十年切 10 个模型；另训 2000–2012 一个；对照 News word2vec 与 Common Crawl GloVe（PDF p.13–14）。
- 技术：word2vec skip-gram，300 维，每十年 ≥25 次词；5 部词典抽反义词对构轴；20 个子样本构 90% 置信区间（PDF p.14）。
- 输出：词×维度投影表；维度×维度夹角矩阵；「结构稳定、标记流动」的双层结论（PDF p.22、p.25）。
- 可迁移点：把「阶级」换成「体制内外」「城乡」「体面」，先确认每条轴两端词在语料中高频共现，再投影；词层 OLS 只作描述（作者自己提醒不是因果，PDF p.19）。**局限必须先写**：语料代表「a relatively elite, 'literary public'」（PDF p.13）。

**T2 概念空间审计（Boutyline & Arseniev-Koehler 2025）**
- 问题：我测的到底是**用法规律**还是**概念特征**？轴的两端是否只差一件事？
- 数据量：不设门槛（这是审计方法）；作者编码 39 篇社会学嵌入论文，另做一项 BERT 形式轴实验（PDF p.6、p.14–15）。
- 技术：概念分析（上下文空间 vs 概念空间）＋文献按「理论需要什么」编码＋形式轴反证实验（PDF p.9、p.14–15）。
- 输出：estimand 声明（测用法还是测特征）；轴的两端平衡表；外部效度标准清单；「这个概念在哪些维度上**不**适用」的稀疏图（PDF p.12–13）。
- 可迁移点：**任何用嵌入的论文，方法节至少要回答三问**——estimand 是什么？轴怎么平衡？外部效度标准是什么？三问不答，T1 的结论不成立。

**T3 历时嵌入＋对齐＋artifact 诊断（Hamilton, Leskovec & Jurafsky 2016）**
- 问题：哪些词变得快、哪些慢？语义变化是否服从统计规律？某两个词是否在靠近？
- 数据量：6 个语料，最小 COHA 4.1×10^8 词／200 年；中文 CHIALL 6.0×10^10 词，**仅 1950–1999**（PDF p.3，Table 1）。
- 技术：PPMI／SVD／SGNS 三种嵌入，对称窗宽 4、300 维，按十年聚合；正交 Procrustes 对齐；线性混合模型（PDF p.3–4、p.7）。
- 输出：词×十年位移量表；成对相似度时间序列；每期「变化最大的十个词」＋真／边缘／artifact 的人工判定（PDF p.5）。
- 可迁移点：**三课**——不对齐就比较，等于测旋转噪声；`male` 的例子说明「语境变了」不等于「意义变了」；封面广告会造出 `special / cover / romance` 这类假发现（PDF p.5）。

**T4 STM 的协变量设计（Roberts, Stewart, Tingley 等 2014）**
- 问题：主题的「谈多少」（prevalence）与「怎么谈」（content）如何随协变量（含实验处理）变化？
- 数据量：ANES 2008 开放题 2,323 位受访者、60 主题（PDF p.16）；理想场景是短文档（10–100 词）、数百至数千篇（判断，据 PDF p.6 的粒度讨论）。
- 技术：半坍缩变分 EM；50 个初值估一次、按下界剔除剩 10 个；按 coherence-exclusivity 前沿选；FREX 标主题（PDF p.5–7、p.10）。
- 输出：每个协变量的 prevalence 效应（带不确定性）；content 效应；文档×主题矩阵；FREX 词＋exemplar 原文（PDF p.10，Fig. 8）。
- 可迁移点：X 放「位置」（处理、世代、城乡），U 放「配置」（教育、身份），同时报两层；**只看 prevalence 会漏掉框架变化**（判断，据 PDF p.4、p.10）。小样本（500 条）时 content 不稳，只报 prevalence（判断，据 PDF p.8–10 的方差讨论）。

**T5 coherence 当筛子（Mimno, Wallach, Talley 等 2011）**
- 问题：我的主题可解释吗？坏主题属于哪类缺陷？
- 数据量：300,000 篇 NIH 摘要；专家从 500 个主题中标注 148 个（PDF p.2–3）。
- 技术：coherence 公式 C(t) = ΣΣ log[(D(v_m, v_l) + 1) / D(v_l)]（PDF p.4，式 1）；共现单位是**文档**，不是句子；用 AP／AUC 与专家判断比较（PDF p.4–5）。
- 输出：每主题一个负值；coherence × exclusivity 散点（每点一个模型）；按 coherence 排序的主题表，尾部即候选丢弃对象。
- 可迁移点：**只保留前 80%，其余写进附录并说明「已剔除不可解释主题」**；同时报主题大小，避免把「小」误当「坏」（PDF p.4）；把四类缺陷（chained／intruded／random／unbalanced）当**发现**而不是错误（PDF p.3）。

**T6 文化环境的穷尽语料（Bail 2014）**
- 问题：一个议题周围**全部相关文本**构成的意义场是什么形状？边界在哪？何时转折？
- 数据量：判据不是「大」，而是「你能说清边界规则」——某数据库的某索引＋某组布尔关键词＋某时段；或起点站＋分类规则＋波数的 snowball（PDF p.5–6）。
- 技术：爬取（screen scraping／API／snowball）→ 聚类或主题模型 → 有监督迭代（「俄罗斯套娃」式多轮编码，PDF p.10）→ 与质性往复。
- 输出：带元数据的语料库；主题/聚类；主题比例时间曲线；可叠加的行动者—话语二模网络（PDF p.11）。
- 可迁移点：**读场的轮廓，不读单个主题**——主题之间是核心—边缘、两极、还是碎片？把「本应出现却没出现」的框架列成一张表，别让它落进 missing（PDF p.9）。作者的三条自我限定必须照抄：缺生产语境、自动编码不会比编码方案更可靠、入门成本高（PDF p.13–14）。

**T7 链接聚类切微类型（Lizardo 2024）**
- 问题：一个粗糙标签内部是否存在有社会意义的亚型？亚型是否**推翻**大类型的结论？
- 数据量：2,263 人 × 20 个音乐大类 = 9,216 条人—品味连线，密度 .20（PDF p.4）。经验下界（判断）：≥1,000 人 × 15 项。
- 技术：二值化（「喜欢且常听」＝1）→ 共享节点连线的 Jaccard 相似度 → 相异度 → Ward 层次聚类 → 按需切枝（PDF p.4–7）。
- 输出：谱系树（高层复现原 20 类，低层裂出微类型）；连线归属表；以微类型为因变量的回归（PDF p.7、p.9）。
- 可迁移点：**聚类连线，不聚类节点**；三步读法——先看高层是否复现原标签（内建自检），再看微类型的**伴随选择**，最后看回归系数是否与大类型不同（PDF p.7–9、p.11）。

**T8 关联规则测方向（Gondal 2025）**
- 问题：品味之间是谁向谁靠拢？谁是统一者、谁是分化者、谁是多义？
- 数据量：SPPA 2017，8,523 人 × 15 项（PDF p.6）。经验下界（判断）：≥1,000 人 × 10 项。
- 技术：`fcaR` 转 transactions → `arules` 的 Apriori → (support, confidence) = (0.02, 0.8) → lift ≥ 3 → 去冗余 → `arulesViz` + Pajek（PDF p.4–5）。
- 输出：规则表（LHS/RHS/support/confidence/lift/count）；有向网络图；前项共现网络；分学历/世代的规则图（PDF p.6）。
- 可迁移点：**「最流行 ≠ 最统一」**——ART 收到 109 条边，NOVELS 最常见却不在中心（PDF p.6）；用互惠边比例判断整体是共同体式还是层级式（判断，据同上）。

> **候补两个**（不做主模板，但值得单列）：**伪项目**（Childress 2025，成本最低，见 §3.6）与**三模态编码**（Ma 2024，可把「情感分析」升级为「偏好／消费／评价」三分编码，见 §3.6）。

---

## 9. 与另两条路线的接口

**接口的哲学依据不是折中，而是「再一次外化」。** Mohr & Rawlings 把 Ricoeur 区分 writing 与 speech 的四条（时间性、主体性、象征化、他者性）整体平移到「数据」与「文本」之间（PDF p.39–41），结论是：**数据分析不是文本分析的降级，而是又一次层级跃迁**。手册第 9 章把这句写成方法承诺：「cultural sociology will be well served by continuing to explore the ways in which formalism and hermeneutics can usefully complement one another」（PDF p.117），并把形式模型定义为包含定性比较分析、编码访谈、主题模型、网络模型的广义概念（PDF p.110–111）。**所以接得上，但接的方式不是「先算后解释」，而是「算本身就是一种读」。**

### 9.1 怎么用计算做布迪厄的场域／资本

**共享的技术接口只有一处**：场域测量＝找该场域特有的资本种类及其分布（Mohr et al. 2020, PDF p.113），主流技术是对应分析／几何数据分析（PDF p.116）。布迪厄自己也用 correspondence analysis（Manovich, PDF p.133–134、p.294–295）。**分歧不在技术，在因果语调**：Manovich 对这种「隔离若干变量、声称它们影响另一些变量」的做法表示警惕，说它让他想起「把艺术当作阶级斗争表达的马克思主义文化社会学」，并称其「highly reductive logic… is obvious」（PDF p.155）。

**具体设计（判断，五步）：「某省会城市文化消费场」**
1. **建二模矩阵**：行动者（按教育×职业×代际分层）× 文化实践（观展、演唱会、读书、短视频、非遗活动……）。数据来源优先级：CGSS 文化模块（2003/2005/2010 等轮次题器可比，Gondal 笔记指其可做）＞ 平台行为日志 ＞ 自采问卷。
2. **对应分析取前两轴**，把「资本种类」读成轴上的极性词（如「体制内雅正」vs「市场潮流」）；**判据**：前两轴的累计解释比例与轴的实质可命名性同时过关。
3. **用 RCA 测图式**：在同一套 Likert 题上按「绝对值距离」聚类，得到共享区分逻辑的人群，再挂社会人口变量（Mohr, PDF p.39–40）。**判据**：聚类出的群体不能与教育/收入分层完全重合——否则你测的是地位，不是图式。
4. **用链接聚类切微类型**：检验每个大类内部是否有反向子群（Lizardo, PDF p.5–7）。**判据**：至少一个微类型的回归系数与大类型**符号相反**，否则这一步没有增值。
5. **做高维检查**：若第三、四轴的夹角结构不可忽略，则二维平面是过度约简（Kozlowski, PDF p.21，Fig. 8）。**判据**：能报出「压到二维后损失了哪几条夹角关系」。

**必须同时写进方法节的三条限制**：
- DiMaggio 式因子得分测的是**自我呈现与自我形象**，不只是文化资本——作者自陈它「would seem to measure self-presentation and self-image as much as actual expertise in high-culture fields」，并称缺陷只会使效应**向下偏**（DiMaggio & Mohr 1985, PDF p.8, p.1238）。
- 题项全部指向西方高雅艺术，在中国会系统性低估实际的合法文化（书法、古典诗词、红色经典、奥数），照搬很可能得到「文化资本无效」的**假结论**（`bourdieu-articles.md` 对该文的批评，判断）。替代路径：Wang & Tai 的「务实的学习禀性（pragmatic learning disposition）」与「技术资本（technical capital）」提示东亚考试体制下存在**非审美**的文化资本亚种（PDF p.16, p.426；PDF p.17, p.427）。
- 布迪厄的「实践逻辑不可形式化」这一面在 2010 年那篇里被整体略过——它要的正是把它形式化（判断，据 Mohr & Rawlings PDF p.25–27 对 DiMaggio 与场域技术的处理）。

### 9.2 怎么用计算做强纲领的符码／叙事

**唯一合法的入口是「对立结构」，不是「主题词表」。** 强纲领的符码是有约束力的二元对立（神圣／凡俗、理性／感性），且有层次：动机层、关系层、制度层，各层正负两极「同侧同源、异侧相斥」；正极被视为神圣并居于社会「中心」，负极被视为凡俗、危险、污染（`strong-program-route.md` 引《公民领域》PDF p.76–81、p.137）。

**具体设计（判断，四步）：「公民领域符码的文本痕迹」**
1. **先造轴，不先跑模型**：为三层各取 4 对，每对造 6–8 组同义词；检查两端词性、数、语域平衡（Boutyline & Arseniev-Koehler, PDF p.12）。
2. **检验「同侧同源、异侧相斥」**：同侧词投影应同号且正相关，异侧应反号。**判据**：若同侧词彼此不相关，说明这 8 组同义词没有共享一个维度，轴不成立（Boutyline, PDF p.11–12 的「两端只差一件事」要求）。
3. **检验「选了 A 就不能选 B」的张力**：用关联规则挖有向蕴含（A→B 强而 B→A 弱，Gondal, PDF p.3），或用互斥/负相关检验。**判据**：若两极词在同一文档里自由共现、且主题模型的 θ 允许任意混合，则这不是符码，只是两套词汇。
4. **补一层结构等价**：用块模型看这些词是否在话语中占同一位置（Mohr & Rawlings, PDF p.33–34）。**判据**：块模型分出的块与理论预期的三层能对上，而不是只分出「高频/低频」两块。

**必须承认的限度**：这套操作测的是「词汇的用法结构」，不是「约束文本的代码」。因果方向相反——代码先于文本并约束文本，而 LDA 假定文本生成主题（判断，据 Blei PDF p.4 注 1 与强纲领的符码定义）。**所以只能说「这是符码的文本痕迹」，不能说「这是符码」。**

### 9.3 为什么「主题 ≠ 符码」这个跳跃不能成立

**原文自己先拒绝了它**：LDA 原注 1——「we make no epistemological claims regarding these latent variables beyond their utility in representing probability distributions on sets of words」（PDF p.4 注 1）。这是**明确的免责声明**，不是后人的批评。

**三条实质性理由**：
1. **结构不同**。符码是**二元对立**，有 polarity、有约束力、有层次；主题是一个**词共现簇**，无对立、无约束、无层次。Mimno 的四类缺陷（chained／intruded／random／unbalanced）恰恰说明主题经常**没有**内在的对立结构（PDF p.3）。
2. **因果方向相反**。符码**先于**文本并约束文本；LDA 假定文本**生成**主题。把主题叫符码，等于把生成方向倒过来。
3. **可解释性不等于文化重要性**。得分最高的主题往往是套话（基金摘要里的「培训项目」），文化信息量最低；真正有张力的主题得分低（Mimno, PDF p.4–5）。用 coherence 筛出来的高分区，恰恰是**最制度化的套话**。

**一个可操作的判据**：**如果两个主题在语料中从不互斥、也从不对立，它们就不是一对符码，只是两个话题。** 符码要求「选了 A 就不能选 B」的张力，而 LDA 的 θ 允许任意混合。

**三种合规的替代用法**：① 主题＝**话语丛**（a cluster of terms that tend to be used together），不声称约束力；② 主题＝**框架的候选**（Bail 把这列为开放问题，PDF p.9），需人工验证；③ 主题＝**符码的指标之一**，但必须另有对立结构的证据（如关联规则的 A→B 与 B↛A，或结构等价块）。

---

## 10. 十二条常见误读与审稿攻击

**① 「你的 K 是怎么定的？」** → **正解**：K 是**粒度选择**，不是估计（Roberts, PDF p.6）；报 3–5 个 K 的**结论稳定性**，用 coherence × exclusivity 前沿选（PDF p.6–7；Mimno, PDF p.4），公开所有候选模型，并写一句「我们不声称存在唯一正确的 K」。**绝不要**只写「用困惑度确定为 12 个主题」——那正是 STM 明确反对的做法（PDF p.6）。

**② 「词嵌入的轴是你自己挑的反义词对，这不是循环论证吗？」** → **正解**：承认轴是**研究者指定的测量工具**，不是算法发现（Kozlowski, PDF p.8–9 从未否认）；公开轴的构造规则与词表全文；报端点平衡检验与 10 对／40 对的稳健性（PDF p.15）；用外部标准（人类评分）证明同构（Boutyline & Arseniev-Koehler, PDF p.13）。四件事齐了，这条攻击就退化为「方法透明度」问题。

**③ 「你的语料不代表你要推断的人群。」** → **正解**：**不要辩解，直接缩小推断范围**。学 Kozlowski 的写法：「we must limit our generalizations to a relatively elite, 'literary public'」（PDF p.13）。把「中国人怎么想」改成「某年某平台某类作者的话语里，X 与 Y 如何关联」——这一步要做在**研究问题**里，不是放在局限节（判断）。配套依据：文本不是人（Stoltz & Taylor, PDF p.30–31）。

**④ 「余弦相似也可能来自句法、拼写、固定搭配，你怎么知道是意义？」** → **正解**：先摆出非语义关联清单（French fries、colour/honour、「CHICAGO, June 10」，Boutyline & Arseniev-Koehler, PDF p.6）；再做**形式轴对照**（构造纯句法／拼写轴，看目标轴是否与之高度相关——他们用 BERT 形式轴测出 >99.5% 的正确侧向率，说明这类污染极强，PDF p.14–15）；再**回读源文本**（抽 20–30 条高/低相似上下文盲编码，PDF p.13–14）；最后报 SimLex-999 而非 WordSim-353（PDF p.13）。

**⑤ 「你的主题不是文化符码，只是词共现。」** → **正解**：**同意，并改写措辞**。把「符码」改成「话语丛」或「框架候选」，再补独立证据：若真有符码主张，须给出**对立结构**的证据（见 §9.3）；引 LDA 原注 1 说明你比原文更谨慎；用 Mimno 的缺陷类型学把 chained／intruded 当发现（PDF p.3）。这是最容易被击倒、也最容易避免的一击。

**⑥ 「时间趋势是语料构成变化，不是语义变化。」** → **正解**：用**体裁平衡**的语料做稳健性检验（Hamilton 用 COHA 对照 Google Books，PDF p.5）；做 artifact 诊断（看变化最大的词是否集中在某类文档、是否与版面词共变，PDF p.5）；区分「义项变了」与「语境变了」（`male` 例）；报每期的文档数、来源分布、平均长度。同一条威胁在词频法上更粗暴：Google Ngram 的「认知扭曲上升」可能只是在测虚构类占比（Stoltz & Taylor, PDF p.28–29）。

**⑦ 「效度只在美国样本上做过，你凭什么用于中国？」** → **正解**：承认这是**外部效度缺口**，并把它写成贡献而非缺陷——中国样本的验证本身就是论文的一部分；做**最小验证**（50–100 个词、30–50 人评分、3–5 条轴，成本极低，Boutyline & Arseniev-Koehler 说 Prolific 类平台可廉价完成，PDF p.13）；特别检查中文失效点（分词粒度、繁简混用、四字成语的固定搭配、称谓词的政治敏感度）（判断）。

**⑧ 「词向量是语料层的，你却谈『人们怎么想』，这是层次谬误。」** → **正解**：把主语从「人们」改成「语料所代表的话语共同体」（Kozlowski 的 "widely shared"，PDF p.2）；若要做个体层推断，必须另有**个体层数据**（调查、实验）把两层接起来——Kozlowski 用 398 人 MTurk 调查做的正是这件事（PDF p.12、p.16）；明确写出「本研究的推断层次是 X，不能下推到 Y」。

**⑨ 「Mohr 等人不是提出了四条测量路径吗？」** → **正解**：没有。2020 年的书是三层×二重性×枢轴；「四」出自 Mohr & Rawlings 2010，且是一个 2×2 范式格（Kroeber／Lévi-Strauss／DiMaggio／White），不是「人／物／关系／网络」四条。**写作纪律见 §2.3**；把两者混用，等于在一篇论文里同时引错两本书的骨架。

**⑩ 「文化分析是数字人文的一个子集。」** → **正解**：**原文相反**。Manovich 说 DH 对他「was both too broad and too narrow」（PDF p.20），并明确拒绝给领域划界（PDF p.27）；三者是功能分工——人文与质性社科＝interpretation，量化社科＝explanation，数据科学＝automation（PDF p.169）。正确的说法是：数字人文用计算方法处理**历史与专业文本**，目标是**阐释**；计算社会科学处理**当代社会现象**，目标是描述、解释与预测（Chen et al., PDF p.39）；文化分析处理**处于规模之中的文化**，目标是**先看见、再质疑范畴**，并明确拒绝把「不可预测的部分」当噪声扔掉（Manovich, PDF p.296）。

**⑪ 「pivot 就是多方法三角验证吧？」／「这本书是混合方法宣言吧？」** → **正解**：两句都错。pivot 是**同一研究过程中分析层次的移动**，其正当性来自「社会世界本身不按层次分层」，不是来自「多测几次更可靠」（Mohr et al., PDF p.153–155）；而且「This book is not merely another call for the integration of qualitative and quantitative traditions」（PDF p.16）。把 pivot 读成三角验证，会把它最有价值的部分（层次间的解释学往返）抹掉。

**⑫ 「我的模型准确率 95%。」** → **正解**：先问三件事——是不是**同一批数据自评**？VanderPlas 用 `n_neighbors=1` 在鸢尾花上训练并在同一批数据上预测，得到 `accuracy_score = 1.0`，然后立刻反问「But is this truly measuring the expected accuracy?」（PDSH, PDF p.501）。是不是**只有文档层 accuracy**？社会科学常要估**比例**，此时该报「比例估计偏差」（Grimmer, PDF p.339）。切分是不是**随机**？随机切分让同平台、同时段、同话题的文本同时进训练与测试，准确率虚高（Siddiqui, PDF p.277–278）。三条都过关，再谈 95%。

> **附：三个次高频攻击，备用。**「预处理呢？」→ 中文必须报告分词器、词典、停用词表、繁简处理、是否去专名；这些选择对结果的影响往往大于模型选择。「可复制性？」→ 固定种子、公开代码与词表、公开每个模型的 coherence、公开预处理脚本（Kozlowski、Hamilton、Roberts、Gondal 都公开了代码或模型，这是本领域通行标准）。「你只报成功的案例吧？」→ Lizardo 的两个案例是按「文献中已有微类型假设」挑的（PDF p.7），Kozlowski 的 race 维度因相关只有 .27 而被放弃（PDF p.16）；**主动报告失败的那条轴／那个案例，比多报一个成功案例更能建立信任**。

---

## 11. 中国研究的接口

**1）可以做：文化消费场与资本结构的对应分析。** 数据：CGSS 文化模块（2003/2005/2010 等轮次，题器是否完全一致须逐年核对）。技术：行动者×实践列联表 → 对应分析 → 前两轴读成斗争轴线（Mohr, PDF p.113、p.116）。**效度风险**：题项清单若照搬西方高雅艺术，会系统性低估中国实际的合法文化（书法、古典诗词、红色经典、奥数）（判断，`bourdieu-articles.md` 对 DiMaggio & Mohr 的批评）；解方是 Wang & Tai 提示的「非审美亚种」——务实的学习禀性、技术资本（PDF p.16, p.426；p.17, p.427）。

**2）可以做：观念极化的历时测量。** Chen 等的示范最直接可用：知乎「中医 vs 西医」44 问、8,162 答、208 万字（2012–2021）；微信 735 篇、234 万字（2014–2021）；Word2Vec 256 维，用 embedding projector 降到 3D 观察点群何时分裂——2015 年前分布均匀、之后明显极化，微信在 2020 年有转折（PDF p.70–72）。**这是国内文化社会学可直接复用的「语义极化」指标**（判断，据其操作）。**效度风险**：两个平台都是高教育、城市、特定年龄段的偏斜样本，被用来代表「中国互联网舆论」是平台选择问题，不是样本量问题（判断，据 PDF p.70）。

**3）可以做：话语场的边界与转折。** 照 Bail 的边界规则写抽样框：某数据库的某索引＋某组布尔关键词＋某时段，或起点站＋分类规则＋波数（PDF p.5–6）；把主题比例曲线与事件史对齐找转折（PDF p.11）。**效度风险**：平台治理造成的语料断点（删帖、关停、迁移）会被读成「文化变迁」——这正是 Stoltz & Taylor 记录的「语料构成伪装成模式」（PDF p.28–29）的中文版本。处置：把断点写进 datasheet，并单列一节讨论「我们看不到什么」。

**4）可以做：微类型与「谁在被平均数掩盖」。** 把 Lizardo 的链接聚类搬到 CGSS/CFPS 的音乐、阅读、休闲题上（PDF p.5–7）。**效度风险**：题目集合决定一切——若问卷只问「喜欢／不喜欢」而不问「是否常做」，二值化规则就没有选择余地，微类型会被噪声主导（判断，据 PDF p.4）。中国调查里「不知道」选项要单独处理：Gondal 的做法是整条删掉，并指出替代方案是「当作拒绝的品味」（PDF p.6）。

**5）可以做：品味的三模态与平台行为日志的对齐。** 点赞≈偏好？收听时长≈消费？评分≈评价？Ma 的三分法逼你把这个问题写出来（PDF p.4）。**实操建议**：同一批对象上同时取「自报喜欢」「行为频次」「评分」三个指标，先算三者的相关矩阵，再决定用哪一个做因变量（判断）。**效度风险**：平台指标混入了推荐算法的选择——「听得最多」可能是「被推得最多」。

**6）可以做：伪项目的本土化。** 中国版伪项目不能用看起来像外国人名的名字（作者五个名字在性别、族裔、时代上有意分布，PDF p.6；在中国会被一眼识破，属判断）。替代：虚构的县城名、老字号、地方剧种、政策名、非遗项目。**关键设计**：必须给「不知道」选项并做培训模块（PDF p.6）；名字要「听起来合理」但不能与真人混淆。**效度风险**：社会赞许与「政治正确」式作答可能比美国更强，且「不知道」的使用率本身受教育与场合影响（作者已证男性比女性少说「不认识」约 17%，PDF p.7）。

**7）中文效度研究的空白（这一条最重要）。** 本批 12 篇方法论文里，只有 Hamilton 等用了中文语料，且**仅 1950–1999、未报告分词方案**（PDF p.3，Table 1；分词方案「未核实」）。也就是说：**中文词嵌入的文化维度轴是否成立、需要哪些调整（分词、成语、称谓、政治委婉语），没有一篇能回答**（判断，据该批笔记的「尚未解决」清单）。四个具体可做的题目：
- **换分词器对下游的影响有多大？** 景只说「影响重大」（p.289），没给量化。取同一语料，jieba 精确 vs pkuseg 新闻模型 vs NLPIR，比 F1 与主题稳定性。
- **中文轴的端点平衡怎么做？** 英文靠词性/数/语域匹配（Boutyline, PDF p.12）；中文还要处理双字/四字节奏、敬语层级、文白混杂。
- **中文情感词典的领域性有多强？** 「同一词汇在不同的词典中可能表现出不同的极性」（景 p.279）；同一词在不同议题上（如「稳定」在金融 vs 政治话语）极性是否翻转，无人系统测过。
- **反讽与隐性评价**：Siddiqui 明确说词典法无法处理 negation/sarcasm（PDF p.161），而**中文反讽在本批文献中完全没有支持**（未核实）。这是一个真空。

**8）制度性约束要写进方法节。** 计算研究在中国面临的不是算力问题，是**语料的可获得性与可留存性**：Grimmer 书里那套以中国社媒审查为贯穿案例的研究（King, Pan & Roberts 系列），其成功高度依赖「可反复回访 URL」这一特定历史窗口与跨境访问条件；本地复现时面临访问、留存与伦理审查的三重约束（判断，据 `compute-books-1.md` 对该案例的评述）。此外，把「审查」操作化为二元（删／未删），恰好落进作者自己警告的「粗粒度测量掩盖灰区」问题（Grimmer, PDF p.342–343）。

---

## 12. 进阶阅读顺序

> 难度标记：★＝能读懂就能上手；★★＝需要一点统计或编程；★★★＝需要方法论文献的底子。**先读能救命的，再读能加分的。**

1. **Silge & Robinson (2017) *Text Mining with R***（★★，入门首选）。用途：用一个数据结构约定（一行一个 token）把「文本分析＝数据整理」讲透；先读 p.15–20 与 p.45–48，理解 tf-idf 为什么只是启发式。**它是工具层，理论厚度最薄，别引它谈方法论。**
2. **景永霞等《Python 中文文本分析》**（★，中文工程第一本）。用途：中文特有的六道工序（清洗、分词、停用词、向量化、词向量、情感）一次过；p.105 的对照实验与 p.279–281 的否定词反例最好用。**注意 OCR 缺代码块，参数一律「未核实」。**
3. **Siddiqui (2025) *Cultural Analytics in R***（★★）。用途：把 Manovich 的纲领翻成 tidyverse 语法；p.146–174 是「从语料到矩阵到模型」的最短可复现链。**引理论请引 Manovich，引流程才引这本。**
4. **Stoltz & Taylor (2024) *Mapping Texts***（★★）。用途：本路线最好的「语言哲学＋工艺」合体；p.14 的「制图而非挖矿」、p.30–31 的「文本不是人」、p.288 的「完整地图悖论」三处必读。**它事实上是 Mohr 那句「topic models are tools for reading」的操作版。**
5. **Grimmer, Roberts & Stewart (2022) *Text as Data***（★★★）。用途：这条路线的**研究设计宪法**；p.43–66（发现/测量/推断三分＋六原则）、p.277–281（测量五原则）、p.338–343（验证）、p.416–418（FPCILV）四段够用半年。**读它是为了知道什么不能做。**
6. **Mohr 等 (2020) *Measuring Culture***（★★★）。用途：地形图；p.12–28（导论）、p.29–43（人）、p.66–78（物）、p.144–159（结论）必读。**读完要能说出「三层×二重性×枢轴」，并知道它没有「四条路径」。**
7. **Mohr & Rawlings (2010) *Four Ways to Measure Culture***（★★★）。用途：坐标系；p.1–14 定两刀、p.16–35 四格、p.39–43 的 Ricoeur 平移。**读它之前先读 §2.2 的表，否则容易把四格当四种技术。**
8. **Manovich (2020) *Cultural Analytics***（★★）。用途：抽样与特征这两个本路线最弱的问题，他讲得最狠；p.116–147（canon 不是 sample）、p.148–175（数据＝对象＋特征、语义鸿沟）、p.169（解释/说明/自动化）、p.296–298（残差即原创）必读。**它几乎不谈效度，别指望它教你验证。**
9. **Blei, Ng & Jordan (2003) *Latent Dirichlet Allocation***（★★）。用途：读原文的注 1 与 p.4 的「k assumed known and fixed」，就知道后来所有「主题＝符码」的话都不是原文说的。**只读 p.1–6、p.15–17、p.20 即可。**
10. **Roberts 等 (2014) STM ＋ Mimno 等 (2011) coherence**（★★★，配对读）。用途：一个修了「不能带协变量」，一个修了「无法评估可解释性」，但**都没修 K**。读完能答「K 怎么定」这一问而不心虚。
11. **Kozlowski 等 (2019) ＋ Boutyline & Arseniev-Koehler (2025)**（★★★，必须配对）。用途：前者教你「语义轴能测出什么」，后者教你「它什么时候测的不是意义」。**只读前者会做出漂亮而错误的论文；只读后者会什么都不敢做。**
12. **Hamilton 等 (2016) ＋ Lizardo (2024) ＋ Gondal (2025)**（★★★，前沿三件套）。用途：时间维度（对齐与 artifact）、关系维度（连线的聚类）、方向维度（有向规则）。三篇合起来，是「分布性」与「关系性」两派目前最成熟的三个代表。
13. **Chen 等 (2026) *Machine Learning in Social Science***（★★）。用途：唯一一本全书用中国数据的方法著作；p.36 的三段式、p.75 的三条自省（无 ground truth／命名即解释／算法复制偏差）最值得抄。**它的效度讨论偏弱，只读它会低估测量问题。**

> **一条读法建议**：这份书单不要顺着读。先读 4（Stoltz）与 5（Grimmer）建立判准，再回头读 1–3 补工艺；然后 6–7 定坐标；8–9 补两个极端（抽样与原文免责）；10–12 进入前沿；13 落地中国。**每读完一本，写一句「它让我不能再做的那件事是什么」——这比写摘要有用。**

---

## 附：与补编的分工（`computational-sociology.md`）

本文件解决「怎么算、怎么验、怎么读」。补编解决另外四件事，遇到下列问题时直接转过去：

| 问题 | 去处 |
|---|---|
| 我说的「文化」到底是哪一类东西？共享是不是它的定义性属性？ | 补编 §2（Lizardo 四类本体论主张） |
| 「解释」怎么拆成可估计的量？态度差异与解释差异怎么分开？ | 补编 §3（归类 P(c\|s) + 联想 P(a\|c)） |
| 人做什么、机器做什么？「计算扎根」有几种？ | 补编 §4（Nelson / Carlsen & Ralund / 陈茁·陈云松 三线对照） |
| 计算社会学在社会学里算哪一支，描述/测量/因果/预测能接到哪一步？ | 补编 §5（Edelmann 等的定位与四种用途） |
