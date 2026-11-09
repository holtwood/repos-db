# 审计方法与字段定义

## 数据来源（2026-11-06 实时采样）

- 账号与组织仓库清单：`gh repo list holtwood --limit 100`、
  `gh api orgs/{org}/repos?per_page=100`
- Fork 上游：`gh api repos/holtwood-forks/{repo}` 的 `parent.full_name`
- ahead/behind：`gh api repos/{upstream}/compare/{branch}...holtwood-forks:{repo}:{branch}`
- 贡献者审计：`gh api repos/{repo}/contributors`
- 链接有效性：HTTP 状态码 + `Location` 头（`curl -sI`），区分 200/301/404
- Fork ahead 提交性质：抽样读取 compare API 返回的 commit message 与作者

## 每个仓库的记录字段

- 当前规范链接（canonical URL，即迁移后的最终归属地址）
- 所属账号或组织；公开/私有状态
- 属性：原创 / Fork / 组织项目
- Fork 上游地址与 ahead/behind 快照
- 主语言；AI Infra 相关性与学习优先级（P0–P3）
- 建议阅读范围（Fork 类）
- 简历可用性
- 最后审计日期

## 收录范围

- 账号概览统计全部仓库（含私有数量，不列私有名称）。
- `data/repos.json` 是主题索引，不是全量镜像：收录全部 Fork、`holtwood-systems` 当前主线、
  `holtwood-arena` 公开赛道、`open-genomics` 与 `holtwood-projects` 的历史代表作，以及个人号
  的原创与索引仓库。其余公开仓库不强行补录，避免为凑数写没有证据的描述。

## 约束

- 私有仓库名称与描述不进入公开文档。
- 竞赛记录（`data/contests.json` / `catalog/competitions.md`）只收录公开可访问的信息：
  比赛名、公开题目页、`problem_id`、难度、评测环境。私有赛事工作区不在公开文档中列举。
- 竞赛数据由 `scripts/generate.py` 渲染，人工不改 `<!-- AUTO:start -->` 标记之间的内容。
- Fork 与上游研读内容不标为个人原创。
- 组织仓库只有通过 contributors 审计确认个人主导后，才在简历语境中表述为个人项目。
- ahead/behind 与链接状态均为审计日快照，随时间漂移；引用时注明日期。

## 运维：索引凭据轮换

索引层的准确性依赖两个用户级 PAT（`GITHUB_TOKEN` 无法跨账号读仓库，也无法读 Star Lists）：

| 仓库 | Secret | 失效表现 |
|---|---|---|
| `holtwood/repos-db` | `AUDIT_TOKEN` | `Run audit` 步骤报 `Bad credentials (HTTP 401)`，数据不再刷新 |
| `holtwood/stars-db` | `STARS_TOKEN` | `Fetch stars` 步骤报 `Bad credentials (HTTP 401)` |

**PAT 会过期，而过期不会有人通知你——索引只会静默变旧。** 因此：

1. 建立 PAT 后记录到期日，到期前轮换，不要把到期日放在脑子里；
2. 轮换后在 Actions 页面手动触发一次 workflow；
3. 确认徽章里的「审计」日期前进到当天，才算轮换完成；
4. 若 `data/repos.json` 的 `audited_at` 落后于今天超过 8 天，按"索引已失效"处理，先修凭据再引用任何数字。
