# HPC 与可迁移能力项目

这些项目不直接属于 LLM Infra，但支撑“性能工程”的通用叙事（C++、并发、SIMD、
压缩、实时系统），在面试中作为背景与辅助证据使用。

<!-- AUTO:start hpc-and-transferable -->
| 项目 | 能力信号 | 使用建议 |
|---|---|---|
| [cpp-high-performance-guide](https://github.com/holtwood-systems/cpp-high-performance-guide) | C++20 性能工程、SIMD、内存优化、基准测试 | 辅助；内容可作面试复习材料 |
| [bitcal](https://github.com/holtwood-projects/bitcal) | C++23、AVX2 位运算 | 低优先级 |
| [ompi](https://github.com/holtwood-forks/ompi) | MPI/分布式通信理论学习参考 | P3，仅通信话题引用 |
| [fq-compressor](https://github.com/open-genomics/fq-compressor) | C++23、oneTBB 并发流水线、CI/Sanitizer、O(1) 随机访问数据结构 | C++ 工程质量辅助项目（P0 辅助） |
| [fastq-tools](https://github.com/open-genomics/fastq-tools) | 零拷贝 I/O、流水线设计 | 辅助 |
| [minibwa-rust](https://github.com/open-genomics/minibwa-rust) | Rust 系统编程、算法重写 | 辅助 |
| [compress-kit](https://github.com/holtwood-projects/compress-kit) | 跨语言压缩算法与二进制级验证 | 低优先级 |
| [cudaimg](https://github.com/holtwood-projects/cudaimg) | CUDA 图像处理 | 可作 CUDA 广度证据 |
| [kvtier](https://github.com/holtwood-systems/kvtier) | memory hierarchy / KV tiering / 结果包审计 | P1 |
| [race](https://github.com/holtwood-arena/race) | 性能工程方法论、单变量实验与证据记录 | P0 公开信号 |
| [kunpeng-s2-conv](https://github.com/holtwood-arena/kunpeng-s2-conv) | SIMD、访存分块、单变量归因 | P1 辅助 |
| [kunpeng-s3-openfoam](https://github.com/holtwood-arena/kunpeng-s3-openfoam) | 应用级 HPC 调研、可修改范围与 A/B 协议 | P2 |
| [cloud-bench](https://github.com/holtwood-projects/cloud-bench) | 云服务器 p99 长尾、%steal 超售检测、指令集检查 | 辅助 |
<!-- AUTO:end hpc-and-transferable -->

## 边界

- 比赛数字只在记录的硬件、编译器与输入下成立；x86 本地结果不外推鲲鹏/昇腾平台。
- `kunpeng-s3-openfoam` 是静态研究，未编译、未上机，不构成性能结论。
- Fork 只作阅读参考，不作为原创项目。
