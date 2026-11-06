# holtwood-systems 组织概览

审计日期：2026-11-06。方法：`gh repo list` / `gh api orgs/{org}/repos` 拉取清单，
`repos/{repo}/contributors` 逐仓核对贡献者。各账号仓库总数见
[README 账号概览](../README.md)。

## 组织架构

| 账号 | 显示名 | 定位 | 成员 |
|---|---|---|---|
| holtwood | Shane / holtwood | 个人主品牌：Profile、索引、私有实验、个人站点与通用工具 | 本人 |
| holtwood-systems | Holtwood Systems | 原创 AI Infra / HPC 系统（P0）：CUDA/Triton、推理运行时、Serving 控制面 | 仅 holtwood |
| holtwood-arena | Holtwood Arena | 比赛与 benchmark：公开赛道 + 私有赛事工作区 | 仅 holtwood |
| holtwood-forks | Holtwood Forks | 上游源码研读副本，无原创项目 | 仅 holtwood |
| holtwood-projects | Holtwood Projects | 历史应用与工具项目，维护模式 | 仅 holtwood |
| open-genomics | Open Genomics | 生信系统软件旧主线，维护模式 | 仅 holtwood |

## holtwood-systems（原创 AI Infra / HPC）

10 个公开仓库（含 1 个归档旧名仓库），贡献者审计仅 holtwood（另有 CI/dependabot bot）。这是当前简历主线；
下列仓库可以如实表述为“个人主导开发”的组织仓库。

<!-- AUTO:start organizations -->
| 仓库 | 语言 | License | 贡献者 | 定位 |
|---|---|---|---|---|
| [cpp-high-performance-guide](https://github.com/holtwood-systems/cpp-high-performance-guide) | C++ | MIT | holtwood | 可运行的 C++20 性能工程指南：示例、基准、VitePress 文档站 |
| [portfolio](https://github.com/holtwood-systems/portfolio) | Markdown | - | holtwood | 系统作品集入口：学习路径、跨仓契约、证据索引与当前缺口 |
| [cuda-foundations](https://github.com/holtwood-systems/cuda-foundations) | C++ | MIT | holtwood + CI bot | L1：CUDA 算子工程学习路径（原 cuda-kernel-academy） |
| [trifuse](https://github.com/holtwood-systems/trifuse) | Python | MIT | holtwood | L2：Triton 算子库 + torch.library 注册 |
| [cuflash](https://github.com/holtwood-systems/cuflash) | CUDA | MIT | holtwood | L3：CUDA C++ FlashAttention 前后向（WMMA） |
| [tiny-llm](https://github.com/holtwood-systems/tiny-llm) | C++ | MIT | holtwood | L4：CUDA 原生 C++ 推理引擎（GGUF/W8A16/分页 KV） |
| [paged-serving](https://github.com/holtwood-systems/paged-serving) | Rust | MIT | holtwood | L4：PagedAttention 分页 KV + Continuous Batching 控制面 |
| [.github](https://github.com/holtwood-systems/.github) | - | - | - | 组织级配置 |
| [open-infra-ai](https://github.com/holtwood-systems/open-infra-ai) | TypeScript | - | - | [archived] 旧组织名重复仓库，内容已由 portfolio 承接 |
| [kvtier](https://github.com/holtwood-systems/kvtier) | Python | - | holtwood | 主动研究：SGLang HiCache / vLLM KV offloading 的分层复现 |
<!-- AUTO:end organizations -->

逐仓定位与简历用法见 [original-projects.md](original-projects.md)；性能数字的硬件/版本/命令
口径见各仓 README 与 [portfolio](https://github.com/holtwood-systems/portfolio) 证据索引。

## holtwood-arena（比赛与 benchmark）

4 个公开仓库（`race`、`kunpeng-s2-conv`、`kunpeng-s3-openfoam`、`.github`）与 25 个私有
赛事工作区。私有工作区不在公开文档中列举，也不因比赛结束自动公开。

2026-11-06：CANN 2026 电力行业算子专场已结束；十月天梯赛与早期 CANN 挑战赛已归档。
公开入口只保留已脱敏、可复现的材料；比赛账号、提交记录与未脱敏题面不进入本仓库。

## holtwood-forks（上游研读副本）

32 个公开仓库，其中 31 个是 fork（另 1 个是组织配置仓 `.github`）。没有原创项目：

- **研读副本**：vllm、sglang、triton、flash-attention 等上游源码，用于加注释、跑最小复现、
  做对照实验；
- **自用/汉化 fork**：Termius 汉化、Typora 主题、AI Gateway 等日常工具。

逐仓上游、ahead/behind 与阅读建议见 [forks-and-translations.md](forks-and-translations.md)。

> 约定：不改写上游历史（不 rebase、不 squash），实验改动只放自己的分支，不推 upstream；
> fork 不构成原创贡献，也不进入作品集计数。

## holtwood-projects（历史应用与工具）

23 个公开仓库 + 1 个私有仓库，维护模式。以完整可运行的工具与应用实验为主
（WebRTC、书签工具、压缩算法、CUDA 图像处理等），详见
[original-projects.md](original-projects.md)。与 AI Infra 主线弱相关，个别
（compress-kit、cudaimg、cloud-bench）可作为辅助证据。

## open-genomics（生信旧主线）

9 个公开仓库 + 4 个私有仓库，维护模式。生物信息是过去的主线，不再是当前重点；
仓库保留可复现性与必要的维护修复，不新增主线功能。fq-compressor / fastq-tools /
minibwa-rust 是 C++/Rust 工程质量与系统能力的历史证据。

## 命名规则与迁移约定

- 登录名：全小写 + 连字符；显示名用标题式（只影响界面，不影响 URL）。
- 仓库名：全小写 + 连字符；Fork 保留上游原名。
- 组织改名后**组织根 URL 返回 404**，但仓库级旧地址仍靠 301 重定向工作；`gh` CLI
  不接受旧组织名，脚本与 workflow 必须使用新名。
- 完整的改名、迁移与失效链接清单见 [retired-and-migrated.md](retired-and-migrated.md)。
