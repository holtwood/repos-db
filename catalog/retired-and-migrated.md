# 已撤销/已迁移仓库与失效链接记录

审计日期：2026-11-06。方法：对公开文档与主页中的旧 URL 做 HTTP 状态 + 301 Location
检查，并用 `gh api repos/...` 响应体里的 `full_name`（而不是状态码）核对真实归属。

## 一、组织改名

| 旧名 | 现行名 | 生效时间 | 说明 |
|------|--------|---------|------|
| open-infra-ai | holtwood-systems | 2026-11-06 | 组织根 URL 404；仓库级旧地址 301 到新名 |
| cannjudge | holtwood-arena | 2026-11-06 | 同上；赛事工作区仍为私有 |
| build-workbench | holtwood-projects | 2026-10-19 | 组织根 404；仓库级 301 |
| deep-dives | holtwood-forks | 2026-10-19 | 同上 |
| CANN-Judge | cannjudge → holtwood-arena | 2026-10-19 / 2026-11-06 | 大写登录名已废弃 |
| vibe-knight | holtwood-projects | 早期 → 2026-10-19 | 曾改为 build-workbench |
| aicl-lab | open-infra-ai → holtwood-systems | 早期 / 2026-11-06 | 旧仓库名与旧组织名都只靠 301 |
| hpc-workbench | （已不存在） | — | 旧仓库已迁出；当前该名称下无组织 |

## 二、仓库改名与转移（公开仓库）

| 旧地址 | 现行地址 | 说明 |
|--------|---------|------|
| open-infra-ai/open-infra-ai | holtwood-systems/portfolio | 组织改名 + 仓库改名 |
| open-infra-ai/aicl-lab | holtwood-systems/portfolio | 早期仓库名 |
| open-infra-ai/cuda-foundations | holtwood-systems/cuda-foundations | 组织改名 |
| open-infra-ai/trifuse | holtwood-systems/trifuse | 组织改名 |
| open-infra-ai/cuflash-attn | holtwood-systems/cuflash | 仓库改名 + 组织改名 |
| open-infra-ai/paged-infer | holtwood-systems/paged-serving | 仓库改名 + 组织改名 |
| open-infra-ai/triton-fused-ops | holtwood-systems/trifuse | 仓库改名 + 组织改名 |
| open-infra-ai/cpp-high-performance-guide | holtwood-systems/cpp-high-performance-guide | 组织改名 |
| open-infra-ai/ai-infra-radar | holtwood/ai-infra-radar | 转回个人号 |
| holtwood/ai-infra-serving | holtwood/ai-infra-serving-study-plan | 仓库改名 |
| holtwood/race | holtwood-arena/race | 迁入比赛组织 |
| holtwood/kunpeng-s2-conv | holtwood-arena/kunpeng-s2-conv | 迁入比赛组织 |
| holtwood/kunpeng-s3-openfoam | holtwood-arena/kunpeng-s3-openfoam | 迁入比赛组织 |
| holtwood-projects/JadeAI | holtwood-forks/JadeAI | 归位为上游 fork |
| holtwood/cloud-bench | holtwood-projects/cloud-bench | 转入历史应用组织 |
| holtwood/wb2api | holtwood-projects/wb2api | 转入历史应用组织 |
| holtwood/fq-compressor | open-genomics/fq-compressor | 生信旧主线 |
| holtwood/fastq-tools | open-genomics/fastq-tools | 生信旧主线 |
| holtwood/micos-2024 | open-genomics/micos-2024 | 生信旧主线 |
| holtwood/wiki-bioinfo | open-genomics/wiki-bioinfo | 生信旧主线 |
| holtwood/awesome-bioinfo-algorithms | open-genomics/awesome-bioinfo-algorithms | 生信旧主线 |
| holtwood/compress-kit | holtwood-projects/compress-kit | 工具项目 |
| holtwood/bookmarks-cleaner | holtwood-projects/bookmarks-cleaner | 工具项目 |
| holtwood/graph-viewer | holtwood-projects/graph-viewer | 工具项目 |
| holtwood/meta-human | holtwood-projects/meta-human | 工具项目 |
| holtwood/mind-gym | holtwood-projects/mind-gym | 工具项目 |
| holtwood/yolo-toys | holtwood-projects/yolo-toys | 工具项目 |
| holtwood/webrtc | holtwood-projects/webrtc-call | 信令在 webrtc-signaling |

CANN 赛事的私有工具层、台账、榜单观察与赛题工作区已统一迁入 `holtwood-arena`。
这些仓库保持私有，公开文档不列举具体仓库名，也不复制账号、提交记录或未脱敏题面。

## 三、已删除仓库（404，无重定向）

| 旧地址 | 处理 |
|--------|------|
| holtwood/sgemm-optimization | 主页移除；SGEMM 主题由 holtwood-forks/SGEMM_CUDA 与 holtwood-systems/cuda-foundations 覆盖 |
| holtwood/the-art-of-hpc-zh | 主页移除（HPC 教材中文翻译，已放弃） |
| holtwood/cursor-rules | 主页移除（后续替代品：holtwood/awesome-cursorrules-zh） |
| holtwood/awesome-claude-skills-zh | 主页移除 |

## 四、DMCA 记录

`holtwood/lsix`：2025-07 因 DMCA 下架，接口返回 **451**。GitHub 不提供删除或转移入口，
账号下保留该记录、不引用其内容，也不计入 GitHub 的公开仓库计数。

> **检测盲区**：仓库转移后 GitHub 会做 301 重定向，`gh api repos/<旧owner>/<repo>`
> 仍可能返回 HTTP 200（响应体内的 `full_name` 才是真实归属）。仅靠 404 检测无法发现
> 转移；`scripts/audit.py` 已按 `full_name` 比对。
