# 已撤销/已迁移仓库与失效链接记录

审计日期：2026-10-19。方法：对文档与主页中出现的每个旧 URL 做 HTTP 状态 + 301 Location
检查（`curl -o /dev/null -w '%{http_code} %{redirect_url}'`），并用 `gh api repos/...`
响应体里的 `full_name`（而不是状态码）核对真实归属。

## 一、已删除仓库（404，无重定向）

| 旧地址 | 处理 |
|--------|------|
| holtwood/sgemm-optimization | 主页移除展示；SGEMM 主题由 holtwood-forks/SGEMM_CUDA（Fork + 中文注释）与 open-infra-ai/cuda-foundations 覆盖 |
| holtwood/the-art-of-hpc-zh | 主页移除展示（HPC 教材中文翻译，已放弃） |
| holtwood/cursor-rules | 主页移除展示（后续替代品：holtwood/awesome-cursorrules-zh） |
| holtwood/awesome-claude-skills-zh | 主页移除展示 |

holtwood/lsix：2025-07 因 DMCA 下架，接口返回 **451**，GitHub 不提供删除或转移入口，
账号下保留该记录、不引用其内容，也不计入 GitHub 的公开仓库计数。

## 二、旧地址已 404：必须使用规范地址

下列旧链接**不能依赖重定向**，文档与脚本必须写现行地址：

| 旧地址 | 现行地址 |
|--------|---------|
| holtwood/fq-compressor | open-genomics/fq-compressor |
| holtwood/fastq-tools | open-genomics/fastq-tools |
| holtwood/micos-2024 | open-genomics/micos-2024 |
| holtwood/awesome-bioinfo-algorithms | open-genomics/awesome-bioinfo-algorithms |
| holtwood/wiki-bioinfo | open-genomics/wiki-bioinfo |
| holtwood/compress-kit | holtwood-projects/compress-kit |
| holtwood/bookmarks-cleaner | holtwood-projects/bookmarks-cleaner |
| holtwood/graph-viewer | holtwood-projects/graph-viewer |
| holtwood/meta-human | holtwood-projects/meta-human |
| holtwood/mind-gym | holtwood-projects/mind-gym |
| holtwood/yolo-toys | holtwood-projects/yolo-toys |
| holtwood/webrtc | holtwood-projects/webrtc-call（信令服务器在 webrtc-signaling） |

## 三、仍靠 301 重定向工作的旧地址（可访问但不规范）

| 旧地址 | 301 目标 | 说明 |
|--------|---------|------|
| `build-workbench/<repo>` | `holtwood-projects/<repo>` | 2026-10-19 组织改名；仓库级 301 有效，组织根 `github.com/build-workbench` 已 404 |
| holtwood/cloud-bench | holtwood-projects/cloud-bench | 仓库转移 |
| holtwood/wb2api | holtwood-projects/wb2api | 仓库转移 |
| holtwood/ai-infra-interview-prep | open-infra-ai/ai-infra-interview-prep | 仓库转移 |
| holtwood/Clay、holtwood/Termius-Pro-zh_CN 等 9 个 fork | holtwood-forks/&lt;repo&gt; | 2026-10-19 移入 fork 组织 |
| open-infra-ai/aicl-lab | open-infra-ai/open-infra-ai | 仓库改名 |
| open-infra-ai/cuflash-attn | open-infra-ai/cuflash | 仓库改名 |
| open-infra-ai/paged-infer | open-infra-ai/paged-serving | 仓库改名 |
| open-infra-ai/triton-fused-ops | open-infra-ai/trifuse | 仓库改名 |

## 四、组织改名

| 旧名 | 现行名 | 生效时间 | 说明 |
|------|--------|---------|------|
| vibe-knight | holtwood-projects | 早期 → 2026-10-19 | 曾改为 build-workbench，2026-10-19 再改为 holtwood-projects |
| build-workbench | holtwood-projects | 2026-10-19 | 组织根 URL 404；仓库级 301 有效 |
| deep-dives | holtwood-forks | 2026-10-19 | 同上 |
| CANN-Judge | cannjudge | 2026-10-19 | 大写登录名废弃，显示名保留 CANNJudge |
| aicl-lab | open-infra-ai | 早期 | 旧仓库 URL 靠 301 工作，文档改用规范地址 |
| hpc-workbench | （已不存在） | — | 旧仓库已迁出（cpp-high-performance-guide → open-infra-ai，bitcal → holtwood-projects），当前该名称下无组织 |
| open-gitnotes | （未采用） | — | 该名称不由本人持有，未使用 |

> **检测盲区**：仓库转移后 GitHub 会做 301 重定向，`gh api repos/<旧owner>/<repo>`
> 仍返回 **HTTP 200**（响应体内的 `full_name` 才是真实归属）。仅靠 404 检测无法发现
> 转移；`scripts/audit.py` 已按 `full_name` 比对。
