# 🗺️ GitHub Repos Hub — holtwood 项目导航

> **本仓库是所有索引层中的唯一权威地图。** 账号职责、仓库归属、竞赛台账与迁移记录以这里为准；
> 其余索引页（[portfolio](https://github.com/holtwood-systems/portfolio)、
> [arena-index](https://github.com/holtwood-arena/arena-index)、
> [holtwood-projects.github.io](https://holtwood-projects.github.io)、各组织的 `.github` Profile）
> 都是按层切分的**视图**，与本文冲突时以本文为准。
> 面向访客的精选入口是 **[imshane.site/projects](https://imshane.site/projects)**。

> 仓库名中的 `db` 指「结构化数据（`data/repos.json`）+ 生成视图」，不是数据库服务；
> 同一命名族的索引还有 `stars-db`、`repos-db-private`。为什么保留这个名字见
> [ARCHITECTURE.md §6](ARCHITECTURE.md)。

审计日期与总量以下方徽章为准（由 `scripts/audit.py` 刷新，方法见 [methodology.md](methodology.md)）。

<!-- AUTO:start badges -->
![审计日期](https://img.shields.io/badge/审计-2026--11--09-4c9) ![仓库总数](https://img.shields.io/badge/仓库-141-4c9) ![公开](https://img.shields.io/badge/公开-90-blue) ![Fork](https://img.shields.io/badge/Fork-31-orange) ![竞赛](https://img.shields.io/badge/竞赛-3-blue) ![赛题](https://img.shields.io/badge/赛题-15-orange) ![文档站](https://img.shields.io/badge/文档站-docsify-8A2BE2)
<!-- AUTO:end badges -->

## 🧭 架构

| 层级 | 账号 / 组织 | 状态 | 职责 |
|------|-------------|------|------|
| 个人主品牌 | [holtwood](https://github.com/holtwood) | 活跃 | Profile、索引、开发环境、个人站点与个人产品（小程序等） |
| 原创系统 | [holtwood-systems](https://github.com/holtwood-systems) | 活跃 | CUDA/Triton 算子、推理运行时、Serving 控制面与可复现证据 |
| 比赛与 benchmark | [holtwood-arena](https://github.com/holtwood-arena) | 活跃 | CANN / FlagOS / Kunpeng / Muse 工作区、题解记录与公开 `race` 实验室 |
| 上游研读 | [holtwood-forks](https://github.com/holtwood-forks) | 常驻 | 上游源码阅读副本与本地补丁分支；不主张原创，不进入作品集计数 |
| 历史应用 | [holtwood-projects](https://github.com/holtwood-projects) | 归档维护 | 可运行的应用与工具项目，只做必要修复 |
| 生信旧主线 | [open-genomics](https://github.com/open-genomics) | 归档维护 | 生物信息与 C++/Rust 系统软件，只做必要修复 |

归属判据、晋升规则、补丁规则、归档条件与命名规则见 **[ARCHITECTURE.md](ARCHITECTURE.md)**。

## ⭐ 主要项目精选

<!-- AUTO:start featured -->
| 项目 | 语言 | 归属 | 定位 |
|---|---|---|---|
| [cuda-foundations](https://github.com/holtwood-systems/cuda-foundations) | C++ | holtwood-systems | CUDA 算子工程学习路径，SGEMM 到可复用推理组件（原 cuda-kernel-academy） |
| [cuflash](https://github.com/holtwood-systems/cuflash) | CUDA | holtwood-systems | 从零 CUDA C++ FlashAttention 前后向（FP16/BF16 WMMA），含 grid.y 越界修复与 causal 跳过优化 |
| [paged-serving](https://github.com/holtwood-systems/paged-serving) | Rust | holtwood-systems | PagedAttention 分页 KV + Continuous Batching 控制面（Rust）；3 并发 e2e 与 llama.cpp greedy 对齐（诚实记录量化差异） |
| [portfolio](https://github.com/holtwood-systems/portfolio) | Markdown | holtwood-systems | holtwood-systems 的系统作品集入口：CUDA/Triton、推理运行时、Serving 与证据导航 |
| [tiny-llm](https://github.com/holtwood-systems/tiny-llm) | C++ | holtwood-systems | CUDA 原生 C++ 推理引擎：GGUF 加载、W8A16 量化、分页 KV；性能数字以仓库当前报告为准 |
| [trifuse](https://github.com/holtwood-systems/trifuse) | Python | holtwood-systems | Triton 算子库（RMSNorm+RoPE/SwiGLU/FlashAttention/SGEMM）+ torch.library 注册 |
| [race](https://github.com/holtwood-arena/race) | Python | holtwood-arena | 性能工程竞赛实验室：Speed Demon / 1BRC / PPC / DIMACS / AHC；数字绑定硬件与证据 |
| [ai-infra-serving-study-plan](https://github.com/holtwood/ai-infra-serving-study-plan) | Markdown | holtwood | AI Infra（LLM serving）学习计划：kernel、vLLM/SGLang 内部与 mini serving engine |
| [cpp-high-performance-guide](https://github.com/holtwood-systems/cpp-high-performance-guide) | C++ | holtwood-systems | 可运行的 C++20 性能工程指南：示例、基准、VitePress 文档站 |
<!-- AUTO:end featured -->

> 按主题索引见下方各分类与[文档站](https://holtwood.github.io/repos-db/)。

## 🏁 竞赛与赛题

只收录**公开可访问**的信息：比赛名、公开题目页、`problem_id`、难度、评测环境；
私有赛事工作区不在本仓库列举。

<!-- AUTO:start competitions-index -->
| 比赛 | 平台 | 赛期 | 题数 | 状态 | 题面页 |
|---|---|---|---|---|---|
| 昇腾AI行业创新大赛——2026电力行业算子专场 | CANNJudge 昇腾算子判题平台 | 2026-09-20 ~ 2026-11-06 | 10 | 已结束 | [题目列表](https://cannjudge.cn/public/2026_electronic) |
| CANNJudge 2026 十月天梯赛 | CANNJudge 昇腾算子判题平台 | 2026-10 | 4 | 已结束 | - |
| 2026 CANN 挑战赛西北赛区初赛 | CANN 挑战赛 | 2026 | 1 | 已归档 | - |
<!-- AUTO:end competitions-index -->

> 2026-11-06：CANN 2026 电力行业算子专场已结束；十月天梯赛与早期 CANN 挑战赛已归档。
> 逐题明细见 **[catalog/competitions.md](catalog/competitions.md)**。

## 📖 文档站与主题索引

可搜索文档站（GitHub Pages）：**https://holtwood.github.io/repos-db/**。

- [竞赛与赛题](catalog/competitions.md)（公开信息）
- [holtwood 个人原创与索引](catalog/holtwood-owned.md)
- [Fork 与上游研读](catalog/forks-and-translations.md)
- [holtwood-systems 组织概览](catalog/organizations.md)
- [原创系统与公开赛道](catalog/original-projects.md)
- [AI Infra 优先级与阅读范围](catalog/ai-infra.md)
- [HPC 与可迁移能力项目](catalog/hpc-and-transferable.md)
- [工具类与非 AI Infra 项目](catalog/tools-and-unrelated.md)
- [已撤销/已迁移仓库与失效链接](catalog/retired-and-migrated.md)

深读笔记：[deep-dives/](deep-dives/) · 审计方法：[methodology.md](methodology.md)

## 账号概览

<!-- AUTO:start accounts -->
| 账号 | 可见仓库 | 公开 | 私有 | Fork |
|------|---------|------|------|------|
| holtwood（个人身份 / 索引 / 私有实验） | 25 | 11 | 14 | 0 |
| holtwood-systems（AI Infra / HPC 系统） | 12 | 9 | 3 | 0 |
| holtwood-arena（比赛与 benchmark） | 35 | 6 | 29 | 0 |
| holtwood-forks（上游研读） | 32 | 32 | 0 | 31 |
| holtwood-projects（历史应用与工具 · 维护模式） | 24 | 23 | 1 | 0 |
| open-genomics（生信旧主线 · 维护模式） | 13 | 9 | 4 | 0 |
<!-- AUTO:end accounts -->

> 口径：账号概览是徽章所示审计日的全量快照（私有仅计数量，不列名称）；下方分类表是
> **主题索引**，收录全部 Fork、当前主线、公开赛道与历史代表作，不追求逐仓穷举。
> 未进入索引的公开仓库不代表不存在。`holtwood/lsix` 因 DMCA 下架（接口返回 451），
> 不计入公开仓库计数，仅在盘点中保留记录。

## 目录结构

```text
catalog/
  competitions.md           # 竞赛与赛题（仅公开信息）
  holtwood-owned.md         # holtwood 个人原创与索引
  forks-and-translations.md # Fork 记录：上游、ahead/behind、阅读建议
  organizations.md          # holtwood-systems 组织概览
  original-projects.md      # 原创系统与公开赛道
  ai-infra.md               # AI Infra 优先级与阅读范围
  hpc-and-transferable.md   # HPC 与可迁移能力项目
  tools-and-unrelated.md    # 工具类与非 AI Infra 项目
  retired-and-migrated.md   # 已删除/已迁移仓库与失效链接
deep-dives/                 # 上游仓库深读笔记
ARCHITECTURE.md             # 分层决策记录：放置判据、晋升、补丁、归档、命名
methodology.md              # 审计方法与字段定义
CHANGELOG.md
```

## 快速导航

- 想看**我的原创系统** → [catalog/original-projects.md](catalog/original-projects.md)
- 想了解**某个 Fork 的架构与学习路径** → [deep-dives/](deep-dives/)
- 想按**学习优先级**排阅读顺序 → [catalog/ai-infra.md](catalog/ai-infra.md)
- 想看**参加过哪些算子竞赛、有哪些赛题** → [catalog/competitions.md](catalog/competitions.md)
- 查**失效/迁移链接** → [catalog/retired-and-migrated.md](catalog/retired-and-migrated.md)

## 职责边界

以下页面都是**视图层**，不各自维护独立的仓库清单；条目归属以本仓库的「架构」表与 `data/repos.json` 为准。

| 仓库 | 职责 |
|------|------|
| repos-db（本仓库） | 仓库盘点、分类、导航、迁移记录、deep-dives |
| [holtwood/holtwood](https://github.com/holtwood/holtwood) | 个人主页与对外入口 |
| [holtwood-systems/portfolio](https://github.com/holtwood-systems/portfolio) | 系统作品集、跨仓契约与证据索引 |
| [holtwood/ai-infra-serving-study-plan](https://github.com/holtwood/ai-infra-serving-study-plan) | 公开的 AI Infra / LLM Serving 学习计划 |
| [holtwood-arena/.github](https://github.com/holtwood-arena/.github) | 比赛与 benchmark 的公开入口 |
| [holtwood-forks/.github](https://github.com/holtwood-forks/.github) | 上游研读范围与边界说明 |
| [stars-db](https://github.com/holtwood/stars-db) | Star 资源分类索引（不复制其内容） |
