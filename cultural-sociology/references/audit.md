# 依据强度与核对说明

> 本文件说明这份 skill 的知识是从什么材料、以多大强度读出来的。**凡引用本 skill 下判断的人，应先看这一页。**

---

## 1. 材料总量（实测，非估计）

| 项目 | 数值 |
|---|---|
| 源文件 | **106 份 PDF**＝桌面「文化社会学」98 份（5 个子目录）+「计算社会学」8 份（2026-10-21 并入） |
| 总页数 | 12,682 页（12,510 + 172） |
| 可抽取正文字符 | 30,057,621（约 3,006 万字） |
| 抽取工具 | PyMuPDF（`fitz`）逐页抽取，保留 `<<<PAGE n>>>` 物理页码 |
| 纯扫描件 | 2 份：Swidler 1986《Culture in Action》（15 页）、Quijano 2000（19 页）→ 已用 RapidOCR（200 dpi）补齐 |
| 部分扫描件 | 1 份：景永霞《Python 中文文本分析》（297 页，逐页密度仅 234 字符，OCR 后仍有个别代码块缺失） |
| 文本质量 | 其余 95 份均有可读文本层；「计算社会学」8 份全部有文本层（172 页 / 537,521 字符，密度正常）；无失败文件 |

---

## 2. 精读强度（按字符加权，诚实口径）

**全书加权精读约 32.7%**（约 984 万字符）。这不是「读完了」，是「按需读透了关键章节」。

| 子目录 | 份数 | 字符量 | 加权精读 | 比例 |
|---|---|---|---|---|
| 布迪厄路线 | 16 | 5.89M | 1.78M | 30.2% |
| 强纲领路线 | 49 | 12.34M | 4.47M | 36.2% |
| 计算测量路线 | 22 | 7.00M | 2.23M | 31.8% |
| 拉蒙的文化分层 | 8 | 4.17M | 0.76M | 18.1% |
| 后殖民理论 | 3 | 0.12M | 0.12M | 100% |
| 计算社会学（补编） | 8 | 0.54M | 0.48M | 90.0% |

**为什么比例不高但结论仍可靠**：被略读的主要是三类内容——长篇经验描述与案例叙事、统计表与附录、文献综述清单。真正承担概念的章节（导论、概念章、方法章、结论）覆盖率显著高于平均值。判断依据：三部路线文件里每一个概念定义都能落到具体 PDF 页，且都由精读笔记交叉核对过。

**为什么不能报「全部读完」**：13 本 200 页以上的专著若逐页读，字符量超过 1,500 万，单次任务无法完成。任何声称「通读 98 份」的说法都是虚假陈述。

### 2.1 逐份精读比例（关键文献）

| 文献 | 页数 | 精读范围 | 比例 |
|---|---|---|---|
| Swartz《Culture and Power》 | 353 | p.56–180、215–218、267–273 + 零散页 | ~45% |
| Bourdieu《Distinction》 | 603 | p.26–43、120–127、184–190、468–481 | ~12% |
| Bourdieu《Outline》 | 284 | p.11–14、87–94、182–195 | ~13% |
| Bennett《Culture, Class, Distinction》 | 340 | p.22–26、30–37、45–52、58–60、65–71、203–210、272–278 | ~18% |
| Alexander《The Meanings of Social Life》 | 309 | 第 1、5 章 + 创伤章 + 结论 | ~30% |
| Alexander《The Civil Sphere》 | 815 | 导论、第 4 章、结论 + 部分经验章 | ~15% |
| Alexander《The Drama of Social Life》 | 275 | p.28–120、174–196 | ~30% |
| 《Cultural Trauma and Collective Identity》 | 327 | 导论 + 南京章 + 各案例结论 | ~25% |
| 《Trauma: A Social Theory》 | 242 | 导论 + 过程章 + 结论 | ~25% |
| 《Iconic Power》 | 259 | 导论 + Alexander 章 + Binder 章 | ~25% |
| 《What Makes a Social Crisis?》 | 183 | T1–T5 + 阻断条件 | ~35% |
| 《Handbook of Cultural Sociology (2nd)》 | 713 | 目录 + 6–10 章 | ~15% |
| Geertz《文化的阐释》（中译） | 521 | 第 1、2、4、8、15 章 | ~20% |
| Mohr《Measuring Culture》 | 213 | 导论 + 理论章 + 各方法章 + 结论 | ~40% |
| Grimmer《Text as Data》 | 513 | 第 1–3 章 + 验证章 | ~25% |
| Stoltz & Taylor《Mapping Texts》 | 326 | 方法章 | ~30% |
| Manovich《Cultural Analytics》 | 386 | 导论 + 第 4–8 章 + 结论 | ~40% |
| Lamont《Money, Morals, and Manners》 | 314 | 导论 + 方法 + 发现章 | ~15% |
| Lamont《Getting Respect》 | 401 | 导论 + 框架 + 结论 | ~15% |
| Lareau《Unequal Childhoods》 | 481 | 导论 + 方法 + 核心章 | ~6% |
| 期刊论文（约 60 篇） | 5–62 | 绝大多数 70–100% | 见各笔记 |
| Nelson《Computational Grounded Theory》 | 40 | p.1–18、22–35 | ~90% |
| Carlsen & Ralund《CGT revisited》 | 16 | p.1–15 | ~95% |
| Edelmann 等《Computational Social Science and Sociology》 | 21 | p.1–15 | ~90% |
| Goldberg & Singell《The Sociology of Interpretation》 | 21 | p.1–17 | ~85% |
| Lizardo《Kinding Culture》 | 13 | p.1–11 | ~90% |
| Lizardo & Jilbert《Organizations and the Structure of Culture》 | 11 | p.1–9 | ~85% |
| 陈云松等《社会预测》 | 25 | p.1–21 | ~85% |
| 陈茁、陈云松《计算扎根》 | 25 | p.1–22 | ~90% |

---

## 3. 已核实的关键事实（修正了流传较广的错误说法）

| 说法 | 实测结果 | 依据 |
|---|---|---|
| 「强纲领有四条纲领」 | 原始版本是**三条**（文化自主 / 解释学重构 / 因果锚定）；「四条」是把第 2 条拆成两半；「No meaning, no society」是后来的追加，不在 2003 清单内 | *Meanings* PDF p.26–28；2024 手册章 PDF p.39 |
| 「强纲领」之名 | 借自科学社会学（爱丁堡学派），**原意相反**；亚历山大从未回应此指控 | McLennan PDF p.9 |
| 「Mohr 等提出测量文化的四条路径」 | 2020 年该书骨架是**三层（人/物/关系）× 二重性 × 枢轴**；「四」出自 Mohr & Rawlings (2010) 的 **2×2 范式格** | *Measuring Culture* PDF p.78；Mohr & Rawlings PDF Table 1 |
| 「Making Sense of Culture 是 Swidler 2001」 | 是 **Patterson 2014**（Annu. Rev. Sociol.） | 该文全文无 Swidler 引述 |
| 「Vaisey 用 MODE 模型」 | 没有。他用 Haidt 社会直觉论 + D'Andrade 联结主义 + Giddens/Bourdieu | Vaisey PDF p.5–8 |
| 「Lizardo 说 Swidler 的实践意识是 declarative」 | 不准确。Lizardo 的批评是 toolkit 只讲清了「陈述↔公共符码」这条边 | Lizardo 2016 PDF p.8 |
| 「文化是工具箱而不是发动机」是 Swidler 的话 | 是**亚历山大评布迪厄**的话 | 周怡 PDF p.9 |
| 「Geertz 用『深描』」 | 中译本作「浓描」；赖尔例子是「眨眼（twitch）vs 递眼色（wink）」 | 《文化的阐释》PDF p.19、p.29 |
| 「《社会生活的戏剧》提出六要素」 | 该书只有分散罗列（p.40 实为八项）；通行「六要素」出自 2004/2011，页码未核实 | *Drama* PDF p.40 |
| 「拉蒙有三套边界工作类型学」 | 无。她给的是三套评价标准 + 边界形式属性；五类型学在《Getting Respect》的污名回应 | Lamont PDF p.46；*Getting Respect* |
| 「Lareau 自称不是布迪厄派」 | 相反。她自认是布迪厄模型的（部分）经验应用 | Lareau PDF p.391 |
| 「Quijano 提出 colonial matrix」 | 该文无此词（Mignolo 的措辞）；也无「两种神话」提法 | Quijano 全文（OCR） |
| 「计算社会学有描述/测量/因果/预测四分法」 | Edelmann 等 (2020) 只有**「解释导向 vs 预测导向」二分**，且把预测排除在综述外；四分是二次归纳 | 该文 PDF p.2 及注 1 |
| 「Goldberg & Singell 提出 interpretation as a variable」 | 他们做的是把解释概率化为 P(c\|s)、P(a\|c)，并给共享度公式；没有这个口号，也没有「嵌入+LLM+人工编码」三角验证的现成方案 | 该文 PDF p.7、p.15 |

---

## 4. 仍标「未核实」的清单（引用前必须回查）

1. **Alexander 2004 / 2011 的六要素编号与页码**——本批材料只有分散罗列。
2. **Turner 四阶段（breach–crisis–redress–reintegration）的原文页码**——亚历山大是转用，不是照搬。
3. **societalization 的系统定义原文出处**（*What Makes a Social Crisis?* 之外，2018 ASR 版未读）。
4. **「四条纲领」的确切出处**——两处原始文本均无编号式四点列表。
5. **Swidler 2001《Talk of Love》与 2008 回应 Vaisey 的原文**——本批只有二手转述。
6. **Lahire 2003 关于「个体禀性 patrimony」的原文**。
7. **Chiang 2022《Study Gods》关于中国精英中等教育「布迪厄式品味不相关」的判断**——经 Wang & Tai 转引。
8. **Mignolo 的「colonial matrix of power」与 Quijano 的差别**。
9. **Mohr & Rawlings 第四格「知识功能」的确切名称**（只确证 representation / heuristic / power 三项）。
10. **中文分词/繁简/反讽/网络新词对测量效度的量化影响**——本批 22 份计算材料几乎未处理，属真实空白。
11. **Geertz「常识作为文化体系」的完整论证**在 *Local Knowledge*（1983），未读。
12. **陈茁／陈云松与 Nelson 是否互引**——本批未见互引，标「（未核实）」；两套同名 CGT 的对照是本 skill 自己做的结构比较。
13. **《Handbook》第二版没有「未来议程」专章**——议程分散在 7 章的 future directions 小节（第 6、19、24、40、41、52、64 章）。

---

## 5. 使用限制（四条）

1. **不要把本 skill 当原文数据库**。它的页码引证指向的是 PDF 物理页，用于定位，不用于替代原文核对。正式写作引用时，须回原文确认版本与页码。
2. **不要把「加权精读 32.7%」读成「可以随便断言」**。凡本 skill 标注「未核实」「判断」「笔记归纳」的地方，都不得写成确定事实。
3. **「计算社会学」8 份里的中文两篇是方法论纲领，不是经验研究**；陈云松等的案例（12582 样本 × 783 变量）只用于示范流程，不能当作「文化测量在中国已被验证」的证据。
4. **中国经验部分多数是「可检验命题」，不是「已有发现」**。素材里真正做中国经验的研究只有 Cui 2026（小镇做题家）、Li 2025（性别冲突）、Meinhof 两篇（校园现代性/落后话语）、Hashimoto（中日战争记忆）等少数几篇；其余「中国接口」是基于理论的推论。

---

## 6. 如何更新

- 新增材料：放入对应子目录（文化社会学五组 → `_soc/`；计算社会学 → `_soc_cs/`，脚本 `_build/extract_cs.py`）→ 追加精读笔记 → 更新本文件 §1、§2 的数字与 §4 清单。
- 修正错误：先改 `canon.md` 与对应路线文件中被引的段落，再改本文件 §3 的勘误表（保留原条目，标注「已修正」而非删除，便于追溯）。
