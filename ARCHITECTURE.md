# 架构决策记录（ADR）：账号与仓库分层

> 状态：生效中 · 最近修订 2026-11-09
> 本文件回答一个问题：**一个新仓库该放哪、什么时候该搬家、什么时候该归档。**

## 1. 切分轴

切分依据是**访客该得出什么结论**，不是语言、不是领域、也不是时间先后：

| 访客的问题 | 该看的地方 |
|---|---|
| 他会写系统代码吗 | `holtwood-systems` |
| 他扛得住真实评测和限时吗 | `holtwood-arena` |
| 这些代码是他自己写的吗 | `holtwood-forks`（明确排除） |
| 他以前做过什么 | `holtwood-projects` / `holtwood-genomics`（归档） |
| 这个人是谁、入口在哪 | `holtwood`（Profile / 索引 / 个人产品） |

按"语言"或"领域"切会同时混进原创与二手代码，把作品集的可信度打薄；按"访客结论"切才让每一层都能被独立验证。**这是唯一需要守住的规则。**

## 2. 放置判据

只有四条，按顺序判断，命中即停：

1. **不是自己写的** → `holtwood-forks`。包括上游研读副本、带本地补丁的实验分支、汉化/移植的衍生作品。
2. **有官方评测、榜单、限时提交** → `holtwood-arena`。包括竞赛工作区、题解记录、判题台账、榜单监视。
3. **是仍在推进的原创系统工作** → `holtwood-systems`。
4. **其余**：属于个人身份/工具/站点/个人产品 → `holtwood`；已停止推进的应用或领域主线 → `holtwood-projects` / `holtwood-genomics`。

判据之外的常见误判：
- "它很完整"不是放进 systems 的理由，**是否仍在推进**才是。
- "它很久了"不是放进归档的理由，**是否还有主线投入**才是。

## 3. 晋升规则（arena → systems）

竞赛产物默认留在 `holtwood-arena`，但满足以下**全部三条**时提升到 `holtwood-systems`：

1. 代码已脱离赛题脚手架，能在仓内独立构建与运行；
2. 有一条能在普通硬件上复现的验证路径（不需要评靶机）；
3. 赛期已结束，且不涉及赛期保密约束。

提升时应在新仓库说明来源赛事与赛题，并在 `holtwood-arena` 留下指向新仓库的说明；**不删除**竞赛工作区。

## 4. 补丁规则（forks）

`holtwood-forks` 允许存在本地补丁分支，但必须满足：

- 组织描述与 Profile 必须写明"允许本地补丁"，不得暗示全部是零改动镜像；
- 补丁分支**不计入作品集**，也不在简历语境中称为个人项目；
- 补丁存活超过两周、且有可复现结果或已向上游提 PR 的，按第 3 条评估是否提升到 `holtwood-systems`；
- 衍生作品（汉化、移植、二次修改）在仓库 README 顶部标注上游与改动范围。

## 5. 归档规则

满足任一即归档，并在描述开头写明 `Archived: superseded by X` 或 `归档：不再推进`：

- 能力已被同领域后继仓库覆盖（例：`bwa-rust` → `minibwa-rust`，`swift-duck` → `fq-compressor`）；
- 领域主线整体停止投入（例：生信主线转入维护模式）；
- 赛期与赛后整理均已结束。

**归档不删除。** 被接管的旧实现是"能力随时间收敛"的证据，删除等于抹掉判断过程。

## 6. 命名规则

- 组织一律 `holtwood-<域>`，全部小写连字符；不接受不带前缀的组织名（会读成社区项目，也会从命名空间里漏出去）。
- 仓库名 = **主体 + 可选类型后缀**，全小写；多词用连字符，单 token 品牌名不加连字符（`bitcal`、`utop`、`wb2api`、`recipegrid`、`cudaimg`）。
- 类型后缀**允许且鼓励**，但必须一个词、能消歧。现行约定（由 141 个存量仓库归纳，不是臆造）：

| 后缀 | 用在 | 现存例子 |
|---|---|---|
| `-db` | 结构化数据 + 生成视图的索引层 | `repos-db` `stars-db` `repos-db-private` |
| `-guide` / `-foundations` | 教学与学习主线 | `cpp-high-performance-guide` `cuda-foundations` |
| `-plan` / `-prep` / `-kit` | 计划、求职资料、工具集 | `ai-infra-serving-study-plan` `career-prep` `agent-skills-kit` |
| `-lab` | 实验体系 | `ascend-llm-infra-lab` |
| `-site` | 站点仓库 | `imshane-site` |
| `-server` | 与同名项目配套的服务端 | `cloud-bench-server` |
| `-minigame` | 微信小游戏（区别于小程序） | `melon-bump-minigame` |
| `-rust` / `-zh_CN` 等 | 同一工具的第二实现 / 本地化变体 | `fq-compressor-rust` `minibwa-rust` |

- 竞赛仓库：`<赛事>-<年份>-<赛道>-<序号>-<题目slug>`，例 `cann-2026-power-04-det`。
- Fork 沿用上游名，不改（`vllm`、`Triton-Puzzles`、`Termius-Pro-zh_CN`）。
- 反面清单：不要把语言写进名字（`xxx-cpp`）；不要造无信息量的泛名（`my-project`、`tools`）；不要在一个功能域里混三种命名风格。
- 已存在的历史命名不为了整齐而批量重命名；只在下次自然触碰该仓库时按本规则改。

### 为什么 `repos-db` / `stars-db` 不改名

`-db` 后缀在本账号里表示「**结构化数据 + 生成视图**的索引层」：`data/*.json` 是事实源，
`scripts/generate.py` 渲染成页面，Pages 提供站点。它和作品集仓库是两个物种，名字要能区分。

评估过改成 `repo-map` / `star-map` 一类，结论是**不改**，理由是可验证的：

- GitHub 官方文档（Renaming a repository）：改名时"除 **project site URLs** 外"全部自动重定向。
  也就是说 `holtwood.github.io/repos-db/` 与 `/stars-db/` 会直接 404，唯一解法是绑自定义域名。
- 两者互相引用，并被 `holtwood`、`holtwood-systems/portfolio`、`holtwood-arena/*`、
  `holtwood-projects.github.io` 共 40+ 处引用。改名收益是审美，成本是断链加书签失效。

**将来若真要改**：先给两个站点绑自定义域名（例如 `map.imshane.site`），URL 与仓库名解耦后再改名；
或改名后用同名仓库放跳转页。在此之前保持原名，不要每次评审重新讨论一遍。

## 7. 可见性与索引

- 私有仓库的名称与描述不进入公开文档，只进入公开统计数字。
- 索引层只有 `repos-db`（公开）与 `repos-db-private`（私有）维护仓库清单；其余页面是视图，冲突时以 `repos-db` 为准。
- 公开文档中出现性能数字时，必须绑定硬件、提交与测量方式；无复现路径的数字标注为"未独立复现"。

## 8. 运维要求

索引的准确性依赖两个定时任务，二者都需要**用户级 PAT**（`GITHUB_TOKEN` 无法跨账号读取，也无法读取 Star Lists）：

| 仓库 | Secret | 用途 | 失效表现 |
|---|---|---|---|
| `holtwood/repos-db` | `AUDIT_TOKEN` | 跨 6 个账号拉取仓库清单与 ahead/behind | 审计步骤报 `Bad credentials (HTTP 401)` |
| `holtwood/stars-db` | `STARS_TOKEN` | 读取 Star 与 Star Lists | `Fetch stars` 步骤报 `Bad credentials (HTTP 401)` |

**PAT 会过期，过期后索引静默变旧。** 轮换后须手动触发一次 workflow，确认徽章日期前进。

## 9. 未决事项

- `open-genomics` 计划更名为 `holtwood-genomics`（GitHub 组织改名只能通过网页端 Settings 完成）。改名后需同步：本文件、`README.md` 架构表、`methodology.md`、`holtwood/holtwood` Profile、`holtwood-genomics` 组织内 4 处 `open-genomics.github.io` 引用。
- `electronic` 组织当前为空组织（0 仓库、无描述），待定：删除，或赋予明确职责（硬件/电子方向）。
