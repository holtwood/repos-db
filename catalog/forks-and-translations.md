# Fork 与上游研读

审计日期：2026-11-06。公开 Fork 记录共 32 条：31 个在 `holtwood-forks`，另 1 条为
`holtwood/lsix` 的 DMCA 状态记录（451，仅作历史记录）。

**重要声明**：这些 Fork 是上游开源项目的阅读副本；只有部分带个人中文注释/翻译，
**不是个人原创项目**，不得写入简历“项目经历”。ahead 提交不构成原创贡献。

<!-- AUTO:start forks-and-translations -->
| Fork | 上游 | ahead/behind | 主语言 | AI Infra 优先级 | 学习价值与建议阅读范围 |
|---|---|---|---|---|---|
| [JadeAI](https://github.com/holtwood-forks/JadeAI) | [LingyiChen-AI/JadeAI](https://github.com/LingyiChen-AI/JadeAI) | 147/2 | TypeScript | 无 | AI 简历/求职工作台 fork；上游 LingyiChen-AI/JadeAI |
| [cuda-samples](https://github.com/holtwood-forks/cuda-samples) | [NVIDIA/cuda-samples](https://github.com/NVIDIA/cuda-samples) | 26/2 | C++ | P1 | CUDA 特性官方示例；只跑 0_Introduction、2_Concepts_and_Techniques、矩阵乘法相关样例 |
| [SGEMM_CUDA](https://github.com/holtwood-forks/SGEMM_CUDA) | [siboehm/SGEMM_CUDA](https://github.com/siboehm/SGEMM_CUDA) | 2/0 | CUDA | P1 | SGEMM 优化阶梯（naive→WMMA）经典教程，已中文化 |
| [cuda-course](https://github.com/holtwood-forks/cuda-course) | [Infatoshi/cuda-course](https://github.com/Infatoshi/cuda-course) | 2/0 | CUDA | P1 | CUDA 入门课程，与 cuda-samples 互补，选其一 |
| [Triton-Puzzles](https://github.com/holtwood-forks/Triton-Puzzles) | [gpu-mode/Triton-Puzzles](https://github.com/gpu-mode/Triton-Puzzles) | 2/0 | Notebook | P1 | Triton 动手练习，第 4 周配合使用 |
| [extension-cpp](https://github.com/holtwood-forks/extension-cpp) | [pytorch/extension-cpp](https://github.com/pytorch/extension-cpp) | 5/1 | Python | P1 | PyTorch C++ 扩展官方模板 |
| [nano-vllm](https://github.com/holtwood-forks/nano-vllm) | [GeeeekExplorer/nano-vllm](https://github.com/GeeeekExplorer/nano-vllm) | 3/0 | Python | P1 | 极简 vLLM 复现，理解 PagedAttention 最短路径 |
| [mini-sglang](https://github.com/holtwood-forks/mini-sglang) | [sgl-project/mini-sglang](https://github.com/sgl-project/mini-sglang) | 6/0 | Python | P1 | 紧凑版 SGLang，理解 serving 主循环 |
| [flash-attention](https://github.com/holtwood-forks/flash-attention) | [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention) | 2/79 | Python/CUDA | P2 | 只读 core 目录 FlashAttention 前向实现 |
| [flashinfer](https://github.com/holtwood-forks/flashinfer) | [flashinfer-ai/flashinfer](https://github.com/flashinfer-ai/flashinfer) | 8/2869 | Python/CUDA | P2 | Kernel 库，对照 triton-fused-ops 的 API 设计 |
| [vllm](https://github.com/holtwood-forks/vllm) | [vllm-project/vllm](https://github.com/vllm-project/vllm) | 14/5091 | Python | P2 | 只读 core scheduler、block manager、worker 主链路 |
| [sglang](https://github.com/holtwood-forks/sglang) | [sgl-project/sglang](https://github.com/sgl-project/sglang) | 12/5571 | Python | P2 | 只读 scheduler 与 router |
| [TensorRT-LLM](https://github.com/holtwood-forks/TensorRT-LLM) | [NVIDIA/TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) | 1/2491 | Python/C++ | P2 | 只读 attention/quantization 文档与 benchmark 目录 |
| [triton](https://github.com/holtwood-forks/triton) | [triton-lang/triton](https://github.com/triton-lang/triton) | 0/696 | MLIR | P2 | 只读 python/triton 语言前端与 tutorial |
| [tvm](https://github.com/holtwood-forks/tvm) | [apache/tvm](https://github.com/apache/tvm) | 1/430 | Python | P3 | 仅投 ML Compiler 岗时读 tensor expression 与 TE 调度 |
| [LightLLM](https://github.com/holtwood-forks/LightLLM) | [ModelTC/LightLLM](https://github.com/ModelTC/LightLLM) | 12/116 | Python | P2 | 轻量推理框架，triton kernel 实现可对照 |
| [lectures](https://github.com/holtwood-forks/lectures) | [gpu-mode/lectures](https://github.com/gpu-mode/lectures) | 3/1 | Notebook | P1 | GPU MODE 讲座材料，性能分析专题 |
| [dataflowr-notebooks](https://github.com/holtwood-forks/dataflowr-notebooks) | [dataflowr/notebooks](https://github.com/dataflowr/notebooks) | 16/0 | Notebook | P3 | 深度学习课程笔记，按需查阅 |
| [LLM-Workshop](https://github.com/holtwood-forks/LLM-Workshop) | [tylerelyt/LLM-Workshop](https://github.com/tylerelyt/LLM-Workshop) | 8/0 | Python | P3 | LLM 应用课程，与 Infra 主线弱相关 |
| [minGPT](https://github.com/holtwood-forks/minGPT) | [karpathy/minGPT](https://github.com/karpathy/minGPT) | 5/0 | Python | P3 | GPT 最小实现，理解 Transformer 结构用 |
| [tutorials](https://github.com/holtwood-forks/tutorials) | [triton-inference-server/tutorials](https://github.com/triton-inference-server/tutorials) | 7/9 | Python | P3 | Triton Inference Server 教程（注意与 Triton 语言区分） |
| [ompi](https://github.com/holtwood-forks/ompi) | [open-mpi/ompi](https://github.com/open-mpi/ompi) | 13/454 | C | P3 | MPI 实现，分布式通信理论参考 |
| [Termius-Pro-zh_CN](https://github.com/holtwood-forks/Termius-Pro-zh_CN) | [ArcSurge/Termius-Pro-zh_CN](https://github.com/ArcSurge/Termius-Pro-zh_CN) | 14/9 | Python | 无 | Termius 汉化中文包；自用 fork，与 AI Infra 无关 |
| [Clay](https://github.com/holtwood-forks/Clay) | [chaun-yi7/Clay](https://github.com/chaun-yi7/Clay) | 0/3 | CSS | 无 | Typora 主题（仿 Claude 配色）；自用 fork，与 AI Infra 无关 |
| [lsix](https://github.com/holtwood/lsix) | - | 0/0 | Shell | 无 | 终端图片预览脚本；2025-07 DMCA 下架，API 返回 451，GitHub 不提供删除/转移入口，仅作记录 |
| [DLX](https://github.com/holtwood-forks/DLX) | [OwO-Network/DLX](https://github.com/OwO-Network/DLX) | 0/15 | Go | 无 | 自建翻译 API 服务；自用 fork，与 AI Infra 无关 |
| [axonhub](https://github.com/holtwood-forks/axonhub) | [looplj/axonhub](https://github.com/looplj/axonhub) | 0/149 | Go | 无 | 开源 AI Gateway（多模型统一接入）；自用 fork，与主线弱相关 |
| [fruit-ninja-dojo](https://github.com/holtwood-forks/fruit-ninja-dojo) | [yongqixue99-hue/fruit-ninja-dojo](https://github.com/yongqixue99-hue/fruit-ninja-dojo) | 0/0 | HTML | 无 | 原生 Canvas 水果忍者小游戏；自用 fork |
| [gpt6-astra-one-shot-games](https://github.com/holtwood-forks/gpt6-astra-one-shot-games) | [Ayi1337/gpt6-astra-one-shot-games](https://github.com/Ayi1337/gpt6-astra-one-shot-games) | 1/0 | HTML | 无 | GPT-6 Astra One Shot 小游戏合集；自用 fork |
| [massCode](https://github.com/holtwood-forks/massCode) | [massCodeIO/massCode](https://github.com/massCodeIO/massCode) | 0/83 | TypeScript | 无 | 开发者工作区（代码片段/笔记/HTTP 请求）；自用 fork |
| [patch-devin](https://github.com/holtwood-forks/patch-devin) | [a0yark/patch-devin](https://github.com/a0yark/patch-devin) | 0/0 | Python | 无 | Devin CLI 系统提示词补丁工具；自用 fork |
| [web_search_devin](https://github.com/holtwood-forks/web_search_devin) | [mimimaster/windsurf-search-mcp](https://github.com/mimimaster/windsurf-search-mcp) | 2/0 | JavaScript | 无 | Devin 服务端 Web 搜索 MCP 服务器；自用 fork |
<!-- AUTO:end forks-and-translations -->

## 阅读建议

- 先读 `mini-sglang` / `nano-vllm` 建立 serving 主循环，再读 `vllm` / `sglang` 的调度与缓存。
- CUDA 路径从 `cuda-samples` / `SGEMM_CUDA` 起步，再看 `flash-attention` / `flashinfer`。
- `triton` 与 `Triton-Puzzles` 分开看：前者是编译器/语言实现，后者是动手练习。
- 自用 fork（Termius、Clay、DLX、axonhub 等）与 AI Infra 主线弱相关，不作为技术证据。
