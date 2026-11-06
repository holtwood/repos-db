# Changelog

本文件遵循 [Keep a Changelog](https://keepachangelog.com/) 格式。

## [2026-11-06]

### Changed
- 仓库导航按新组织架构重排：`holtwood`（个人主品牌）、`holtwood-systems`（AI Infra / HPC）、
  `holtwood-arena`（比赛与 benchmark）、`holtwood-forks`（上游研读）、`holtwood-projects`
  （历史应用）、`open-genomics`（生信旧主线，维护模式）。
- `open-infra-ai` → `holtwood-systems`、`cannjudge` → `holtwood-arena` 的组织改名与仓库
  归属同步到账号统计、链接与迁移记录；旧组织根 404，仓库级旧地址仍靠 301。
- README 精选区改为当前主线优先，生信旧主线退出首屏；`holtwood-owned.md` 只列个人号
  原创仓库，迁入组织的 `cpp-high-performance-guide` 归入 `holtwood-systems` 组织表。
- 竞赛索引收口：CANN 2026 电力行业算子专场结束；十月天梯赛补 4 道公开题目页；
  2026 CANN 挑战赛西北赛区初赛归档。私有赛事工作区不因比赛结束公开，也不在文档中列举。

## [Unreleased] — 2026-11-03

### Fixed
- README 两处指向 `open-infra-ai/ai-infra-interview-prep` 的失效公开链接：该仓已于 2026-10-25 迁回 `holtwood` 并转私有，改为按私有仓表述（职责边界表同步）。
- `JadeAI` 实为 `LingyiChen-AI/JadeAI` 的 fork，自 `holtwood-projects` 迁回 `holtwood-forks`，repos.json 同步修正 account/property/upstream。

### Added
- README 职责边界表新增 [holtwood/race](https://github.com/holtwood/race)：性能工程竞赛实验室（Speed Demon / 1BRC / PPC / DIMACS / AHC）。
- 数据快照更新（2026-11-03，audit.py）：补录 `race`（holtwood-owned / hpc-and-transferable）与 `cmdc-statusline`（holtwood-owned / tools-and-unrelated）；21 处字段刷新（ahead/behind、可见性、账号计数）。

## [Unreleased] — 2026-08-19

### Added
- 新增 `data/contests.json` + `catalog/competitions.md`：竞赛与赛题索引（比赛信息、
  公开题目页、`problem_id`、难度）。README 增加"竞赛与赛题"区块与徽章，侧边栏增加条目。
  只收录公开可访问信息，私有解题仓库名称与路径不进入本仓库。

### Changed
- 组织改名终稿落地：build-workbench→holtwood-projects、deep-dives→holtwood-forks、CANN-Judge→cannjudge；9 个个人号 fork 迁入 holtwood-forks，账号计数、链接与迁移记录同步
- 数据快照更新（2026-09-10）：ahead/behind 与链接状态已刷新
- 账号迁移:LessUp → holtwood(repos-db);README 主页化 + GitHub Pages 部署
- 新增 README 主要项目精选区(render_featured)与 GitHub Pages 文档站部署(pages.yml)

- 恢复本仓库作为**独立仓库导航中心**的职责：README 从"已合并跳转页"重写为导航首页，
  含账号概览、目录结构与职责边界表。
- 新增 `catalog/` 八个分类文件（lessup-owned / forks-and-translations / organizations /
  original-projects / ai-infra / hpc-and-transferable / tools-and-unrelated /
  retired-and-migrated），基于 2026-08-19 GitHub API 实时数据。
- Fork 目录记录 22 个 Fork 的上游、ahead/behind 快照与中文注释性质说明。
- 组织仓库全部通过 contributors 审计，确认个人主导的项目清单。
- 新增 `methodology.md` 记录审计方法与字段定义。

### Removed

- 删除被 `catalog/` 取代的旧扁平分类文件：ai-infra-core.md、ai-infra-auxiliary.md、
  hpc-and-systems.md、personal-projects.md、tools-and-others.md、repo-index.md、
  learning-path.md（与 ai-infra-interview-prep 中同名文件逐字节相同，经 diff 验证；
  learning-path 属于学习计划，保留在 ai-infra-interview-prep）。

### Unchanged

- `deep-dives/`（21 个仓库深读笔记）保留在本仓库，作为唯一事实来源；
  ai-infra-interview-prep 中的相同副本已在该仓库删除（见其 CHANGELOG）。
