# 原创系统与公开赛道

审计日期：2026-11-06。贡献者数据来自 GitHub contributors API；仅 holtwood（含 bot）
的项目可表述为个人主导。**这是简历“项目经历”的候选池。**

## holtwood-systems + holtwood-arena

`holtwood-systems` 是原创系统主线；`holtwood-arena` 是比赛与公开性能信号。
两者都不包含 fork，也不把私有赛事工作区写成公开项目。

贡献者审计：`holtwood-systems` 全部公开仓库仅 holtwood（+ CI/dependabot bot）；
`holtwood-arena` 的公开仓库同样由 holtwood 维护。

<!-- AUTO:start original-projects -->
| 项目 | 归属 | 定位与证据 | 简历用法 |
|---|---|---|---|
| [portfolio](https://github.com/holtwood-systems/portfolio) | holtwood-systems | holtwood-systems 的系统作品集入口：CUDA/Triton、推理运行时、Serving 与证据导航 | 讲述入口 |
| [cuda-foundations](https://github.com/holtwood-systems/cuda-foundations) | holtwood-systems | CUDA 算子工程学习路径，SGEMM 到可复用推理组件（原 cuda-kernel-academy） | Kernel 主项目之一 |
| [trifuse](https://github.com/holtwood-systems/trifuse) | holtwood-systems | Triton 算子库（RMSNorm+RoPE/SwiGLU/FlashAttention/SGEMM）+ torch.library 注册 | Kernel 主项目之一 |
| [cuflash](https://github.com/holtwood-systems/cuflash) | holtwood-systems | 从零 CUDA C++ FlashAttention 前后向（FP16/BF16 WMMA），含 grid.y 越界修复与 causal 跳过优化 | Kernel 主项目之一 |
| [tiny-llm](https://github.com/holtwood-systems/tiny-llm) | holtwood-systems | CUDA 原生 C++ 推理引擎：GGUF 加载、W8A16 量化、分页 KV；性能数字以仓库当前报告为准 | 推理系统主项目 |
| [paged-serving](https://github.com/holtwood-systems/paged-serving) | holtwood-systems | PagedAttention 分页 KV + Continuous Batching 控制面（Rust）；3 并发 e2e 与 llama.cpp greedy 对齐（诚实记录量化差异） | 与 tiny-llm 组成推理系统主项目 |
| [kvtier](https://github.com/holtwood-systems/kvtier) | holtwood-systems | KV Cache 分层研究：单卡 L2 微基准与上游 HiCache 贡献 | 系统研究项目 |
| [race](https://github.com/holtwood-arena/race) | holtwood-arena | 性能工程竞赛实验室：Speed Demon / 1BRC / PPC / DIMACS / AHC；数字绑定硬件与证据 | 性能工程公开信号 |
| [kunpeng-s2-conv](https://github.com/holtwood-arena/kunpeng-s2-conv) | holtwood-arena | Kunpeng S2 FP32 2D convolution 优化：x86 本地 ×17–21.6；鲲鹏平台未复测 | HPC 辅助 |
| [kunpeng-s3-openfoam](https://github.com/holtwood-arena/kunpeng-s3-openfoam) | holtwood-arena | OpenFOAM v2606 simpleFoam 静态研究；未参赛、未上机，已归档 | HPC 调研样本 |
<!-- AUTO:end original-projects -->

性能数字的硬件/版本/命令口径见各仓 README 与
[portfolio](https://github.com/holtwood-systems/portfolio) 证据索引，此处不复制。

## open-genomics — 旧主线（维护模式）

生物信息是过去的主线，不再是当前重点。贡献者审计：fq-compressor、fastq-tools 等
contributors 仅 holtwood（micos-2024 另有 dependabot）。仓库保留可复现性与维护修复，
不新增主线功能。

<!-- AUTO:start original-projects-genomics -->
| 项目 | 定位 | 简历用法 |
|---|---|---|
| [fq-compressor](https://github.com/open-genomics/fq-compressor) | C++23 高性能 FASTQ 压缩：3.97x 压缩比、O(1) 随机访问、oneTBB 并发流水线、CI/Sanitizer | C++ 工程质量辅助项目 |
| [fastq-tools](https://github.com/open-genomics/fastq-tools) | FASTQ 质控工具：零拷贝 I/O、TBB 流水线 | C++ 工程辅助 |
| [minibwa-rust](https://github.com/open-genomics/minibwa-rust) | Rust 重写 BWA 序列比对核心 | 系统能力辅助 |
| [fq-compressor-rust](https://github.com/open-genomics/fq-compressor-rust) | fq-compressor 的 Rust 版本 | 辅助 |
| [micos-2024](https://github.com/open-genomics/micos-2024) | 宏基因组综合分析平台（猛犸杯 2024 参赛项目） | 历史项目 |
| [wiki-bioinfo](https://github.com/open-genomics/wiki-bioinfo) | 中文生物信息知识库 | 社区贡献展示 |
| [awesome-bioinfo-algorithms](https://github.com/open-genomics/awesome-bioinfo-algorithms) | 算法知识库 + CLI 维护工具 | 低优先级 |
<!-- AUTO:end original-projects-genomics -->

## holtwood-projects — 历史应用与工具（维护模式）

23 个公开仓库 + 1 个私有仓库；组织仅一名成员。与 AI Infra 主线弱相关，仅在对应话题中
作为辅助证据：

- [compress-kit](https://github.com/holtwood-projects/compress-kit)（C++/Go/Rust 跨语言压缩算法与二进制验证，P2）
- [cudaimg](https://github.com/holtwood-projects/cudaimg)（CUDA 图像处理，P2）
- [cloud-bench](https://github.com/holtwood-projects/cloud-bench)（云服务器 p99 长尾、%steal 超售检测，P2）
- [webrtc-signaling](https://github.com/holtwood-projects/webrtc-signaling) / [webrtc-call](https://github.com/holtwood-projects/webrtc-call)（Go 实时系统背景）
- 其余（bookmarks-manager、bookmarks-cleaner、graph-viewer、mind-gym、meta-human、
  yolo-toys、utop、chatroom、shadow-note）为工具/应用实验，P3，不进入 AI Infra 简历主线。

> `awesome-compression` 由个人号 [holtwood](https://github.com/holtwood/awesome-compression)
> 维护；`JadeAI` 是 fork，归在 [holtwood-forks](https://github.com/holtwood-forks/JadeAI)；
> `cmdc-statusline` 在个人号 [holtwood](https://github.com/holtwood/cmdc-statusline)。
