# Changelog

## v1.1.3
- **删除文献出处说明**：移除 SKILL.md 末尾的出处清单整段与其后的机读说明。
- **去除轮次痕迹**：`cheatsheet.md` 第八节改为「进阶要点（先定期刊 / 结构 / 摘要 / 引言 / 结果）」；`references/01–09` 九处「## 增补：…」标题去掉「增补」前缀，正文内容不变。
- 正文中的作者归属标签（彭玉生、张静、Machi、Becker、易莉、Strunk、Martín、Edwards、Kail 等）保留，正文实质内容未改写。
- README 同步清理相应用语。

## v1.1.1
- **修复平台上传报错「目录层级超限」**：把 `assets/templates/*.md` 上移为 `templates/*.md`，全包现在只有两级目录（根文件 + `references/` + `templates/`），深度 = 2。
- 同步改写 SKILL.md 与 references/01–11 中的 12 处路径引用；`name`/内容不变。
- 打包脚本新增目录深度硬校验（`max dir depth <= 2`），避免同类问题复发。

## v1.1.0
- 新增 `references/11-期刊选择与投稿适配.md` 与 `templates/期刊选择.md`（v1.1.1 起由 `assets/templates/` 上移）。
- references/01–09 补充：Edwards 八个心智动作、Kail 五种引言钩子与结果呈现、Martín 摘要六条与 IBC 比例、相关性三支柱。
- frontmatter 改为平台可上传的七字段（name/version/display_name/display_name_en/description/description_zh/description_en）。

## v1.0.0
- 首次发布：按论文环节组织 10 个模块 + 速查表 + 9 个模板。
