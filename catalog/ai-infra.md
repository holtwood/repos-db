# AI Infra 视角：优先级与阅读范围

原则：**“行业重要性”与“是否完整读源码”分开评价**。不做大仓全仓通读，只读与当前问题
相关的调用链和数据结构。

## P0 — 原创系统与公开信号（holtwood-systems / holtwood-arena）

| 项目组 | 仓库 | 证据形态 |
|--------|------|---------|
| 推理系统 | [paged-serving](https://github.com/holtwood-systems/paged-serving) + [tiny-llm](https://github.com/holtwood-systems/tiny-llm) | 控制面/数据面 C ABI、分页 KV、continuous batching、端到端差分 |
| Ascend NPU 实验（个人号，候选迁入 systems） | [ascend-llm-infra-lab](https://github.com/holtwood/ascend-llm-infra-lab) | 910B2 vLLM 基线、KV 账本、goodput/SLO、调度消融、量化与多副本扩展（50+ 实验） |
| Kernel | [cuda-foundations](https://github.com/holtwood-systems/cuda-foundations) + [cuflash](https://github.com/holtwood-systems/cuflash) + [trifuse](https://github.com/holtwood-systems/trifuse) | CUDA/Triton/FlashAttention、差分测试、benchmark、性能分析 |
| KV 分层研究 | [kvtier](https://github.com/holtwood-systems/kvtier) | SGLang HiCache L2 微基准、结果包审计、上游贡献边界 |
| C++ 工程辅助 | [cpp-high-performance-guide](https://github.com/holtwood-systems/cpp-high-performance-guide)、[fq-compressor](https://github.com/open-genomics/fq-compressor) | C++20/23、SIMD、并发流水线、CI/Sanitizer |
| 公开性能信号 | [race](https://github.com/holtwood-arena/race)、[kunpeng-s2-conv](https://github.com/holtwood-arena/kunpeng-s2-conv) | 单变量实验、硬件绑定、可复现基线 |

## P1 — 选择性动手学习（Fork，只读相关模块）

SGEMM_CUDA、cuda-samples、cuda-course、extension-cpp、Triton-Puzzles、
nano-vllm、mini-sglang、lectures（详见 [forks-and-translations.md](forks-and-translations.md)）。

## P2 — 架构与实现参考（行业价值高，只产出“五个一”）

flash-attention、flashinfer、vllm、sglang、TensorRT-LLM、triton、LightLLM。

每个 P2 仓库只形成：

1. 一张架构图
2. 一条关键调用链
3. 两到三个核心数据结构
4. 一个可运行实验
5. 五个面试问题

产出落在公开的 [ai-infra-serving-study-plan](https://github.com/holtwood/ai-infra-serving-study-plan)
对应周文件；不引用私有面试材料。

## P3 — 按需或低优先级

minGPT、LLM-Workshop、dataflowr-notebooks、tutorials（Triton Inference Server）、ompi、tvm。

- TVM 仅在明确投递 ML Compiler 岗时提升为主线，否则保持选修。
- 非 AI Infra 项目（生物信息、工具类）见 [original-projects.md](original-projects.md)、
  [tools-and-unrelated.md](tools-and-unrelated.md)，不进入核心路线。
