# 组织仓库概览与贡献审计

审计日期：2026-10-19。方法：`gh api orgs/{org}/repos` 拉取清单 + `repos/{repo}/contributors`
逐仓核对贡献者。各账号仓库总数见 [README 账号概览](../README.md)（由 `data/repos.json`
渲染，每周自动刷新）。

## 账号分工

登录名一律**全小写 + 连字符**，显示名用驼峰/标题式（大写只出现在界面展示）；
仓库名一律**全小写 + 连字符**，Fork 保留上游原名。

| 账号 | 显示名 | 定位 | 成员 |
|---|---|---|---|
| holtwood | （个人身份） | 个人主页与索引：Profile、repos-db / stars-db、个人站点、中文社区资源列表 | 本人 |
| open-infra-ai | Open Infra AI | AI Infra 作品集主线（P0）：CUDA/Triton 算子、推理引擎、服务化控制面 | holtwood、Lumkai、TideTree |
| open-genomics | Open Genomics | 生物信息与 C++/Rust 工程能力（P0 辅助） | 仅 holtwood |
| holtwood-projects | Holtwood Projects | 完整可运行的工具与教学项目（P2/P3） | 仅 holtwood |
| holtwood-forks | Holtwood Forks | 上游研读副本与自用 fork，无原创项目 | 仅 holtwood |
| cannjudge | CANNJudge | Ascend C 赛事归档（私有为主） | 仅 holtwood |

## open-infra-ai（AI Infra 作品集）

组织成员 3 人，但**全部 9 个公开仓库的代码贡献者仅为 holtwood**（另含
dependabot[bot]/github-actions[bot]），因此下列仓库可以如实表述为"个人主导开发"的组织仓库。

<!-- AUTO:start organizations -->
| 仓库 | 语言 | License | 贡献者 | 定位 |
|---|---|---|---|---|
| [open-infra-ai](https://github.com/open-infra-ai/open-infra-ai) | Markdown | - | holtwood | 五仓作品集 landing 页与计划/面试材料唯一权威源 |
| [cuda-foundations](https://github.com/open-infra-ai/cuda-foundations) | C++ | MIT | holtwood + CI bot | L1：CUDA 算子工程学习路径（原 cuda-kernel-academy） |
| [trifuse](https://github.com/open-infra-ai/trifuse) | Python | MIT | holtwood | L2：Triton 算子库 + torch.library 注册 |
| [cuflash](https://github.com/open-infra-ai/cuflash) | CUDA | MIT | holtwood | L3：CUDA C++ FlashAttention 前后向（WMMA） |
| [tiny-llm](https://github.com/open-infra-ai/tiny-llm) | C++ | MIT | holtwood | L4：CUDA 原生 C++ 推理引擎（GGUF/W8A16/分页 KV） |
| [paged-serving](https://github.com/open-infra-ai/paged-serving) | Rust | MIT | holtwood | L4：PagedAttention 分页 KV + Continuous Batching 控制面 |
| [.github](https://github.com/open-infra-ai/.github) | - | - | - | 组织级配置 |
<!-- AUTO:end organizations -->

逐仓定位与简历用法见 [original-projects.md](original-projects.md)；性能数字的硬件/版本/命令
口径见各仓 README 与 [open-infra-ai](https://github.com/open-infra-ai/open-infra-ai) 证据包。

## open-genomics（生物信息与 C++ 工程）

组织成员：仅 holtwood。9 个公开仓库（fq-compressor、fastq-tools、minibwa-rust、
fq-compressor-rust、micos-2024、wiki-bioinfo、awesome-bioinfo-algorithms 等）另有 4 个
私有仓库，信息不公开。其中 fq-compressor / fastq-tools / minibwa-rust 是 C++/Rust
工程质量与生物信息背景的核心证据。

## holtwood-projects（实验性与工具项目）

组织成员：仅 holtwood。原名 `build-workbench`（更早为 `vibe-knight`），2026-10-19 改为现名。
25 个公开仓库 + 1 个私有仓库，以完整可运行的工具与应用实验为主（WebRTC、书签工具、
压缩算法、CUDA 图像处理等），详见 [original-projects.md](original-projects.md)。
与 AI Infra 主线弱相关，个别（compress-kit、cudaimg）可作为辅助证据。

## holtwood-forks（上游研读副本与自用 fork）

组织成员：仅 holtwood。原名 `deep-dives`，2026-10-19 改为现名。31 个公开仓库全部是 fork，
没有原创项目：

- **研读副本**：vllm、sglang、triton、flash-attention 等上游源码，用于加注释、跑最小复现、
  做对照实验；
- **自用/汉化 fork**：Termius 汉化、Typora 主题、AI Gateway 等日常工具。

逐仓上游、ahead/behind 与阅读建议见 [forks-and-translations.md](forks-and-translations.md)。

> 约定：不改写上游历史（不 rebase、不 squash），实验改动只放自己的分支，不推 upstream。

## cannjudge（Ascend C 赛事归档）

组织成员：仅 holtwood。原名 `CANN-Judge`，2026-10-19 改为现名。公开仓库 1 个
（`.github` 组织配置），17 个私有仓库为 2026 年 CANNJudge 赛题解题仓与共享基础设施
（`2026-challenge-<slug>`、`2026-power-NN-<slug>`、`2026-ladder-NN-<slug>`、`shared-infra`、
`ledger`），赛题与进度索引见私有对照页（repos-db-private，不公开）。

## 命名规则与迁移约定

- 登录名：全小写 + 连字符，旧的大写名（`CANN-Judge`）已废弃
- 显示名：Open Infra AI、Open Genomics、Holtwood Projects、Holtwood Forks、CANNJudge
- 仓库名：全小写 + 连字符；赛题仓 `2026-<赛道>-<序号>-<slug>`
- 组织改名后**组织根 URL 返回 404**，但仓库级旧地址仍靠 301 重定向工作；301 对 `gh` CLI
  无效（`gh repo list <旧组织名>` 直接报错），脚本与 workflow 必须使用新名
- 完整的改名、迁移与失效链接清单见 [retired-and-migrated.md](retired-and-migrated.md)
