# 企业管理专家团 · 安装与使用说明

> 版本 1.0.1（2026-09-01）｜六位专家：mg-lead 总控 / mg-strategy 战略 / mg-model 商业模式 / mg-growth 增长 / mg-org 组织 / mg-review 复盘

## 这是什么

一组对话式咨询 skill：企业家（中小企业主/创业者）对自己的公司提出困惑，总控专家接诊——先把模糊主诉聚焦成一个真问题、建立企业档案，再分诊给对应领域的专家深挖，最后以「可量化 + 跟进人 + 复查日」的行动承诺收口。跨会话累积咨询档案。

**适用平台**：任何支持 agentskills.io 规范（SKILL.md + frontmatter）的 agent 环境——Claude Code、WorkBuddy 等。纯对话型 skill，不依赖任何专有工具调用。

## 安装

### Claude Code
```bash
# 用户级（所有项目可用）：装到 ~/.claude/skills/
# 项目级（仅当前项目）：装到 <项目>/.claude/skills/
# 把本包 skills/ 下六个 mg-* 目录复制过去，外加 GLOSSARY.md：
cp -r skills/mg-* ~/.claude/skills/
cp GLOSSARY.md ~/.claude/skills/
```

### 其他 agentskills.io 兼容平台（如 WorkBuddy）
按平台文档找到 skill 目录（通常为 `~/.agents/skills/` 或应用内 skill 管理入口），同样放置六个 `mg-*` 目录与 `GLOSSARY.md`。每个 skill 自包含，可独立安装，但六位合装才有完整分诊闭环。

### 企业档案存放
专家会按平台自适应处理：有文件读写能力的环境落盘 `咨询档案/<企业简称>-档案.md`；无文件能力的环境会在会话末输出档案全文，请自行保存、续诊时粘贴回来。档案含敏感经营数据，仅存本地。

## 使用（三种开始方式）

1. **直接说困惑**（推荐）：对 AI 说「我公司的生意增长没劲」「人留不住」——总控专家 mg-lead 会接诊、聚焦问题、建档分诊
2. **点名专家**：如「让商业模式专家看看我这个生意」
3. **续诊**：把上次档案粘贴回来，说「接着上次聊」——专家会先核对上次行动承诺的兑现情况

## 专家团编制

| 专家 | 管什么 |
|---|---|
| mg-lead 总控 | 接诊：聚焦真问题 → 建档 → 分诊 → 行动承诺收口 |
| mg-strategy 战略 | 方向与定位：看不懂外面（市场洞察）、定不了里面（定位/必赢之战） |
| mg-model 商业模式 | 生意设计：画布四问、关键假设、十大坑体检、微创新 |
| mg-growth 增长 | 增长引擎：堵点拆解、流程病诊断、价值流图 |
| mg-org 组织 | 人与组织：激励归因（先查土壤再怪种子）、人才盘点 |
| mg-review 复盘 | 经营节奏：复盘四步法、复盘会四大坑、业绩结构拆解 |

## 发布到 SkillHub（可选）

1. 注册 skillhub.cn + 实名认证 + 创建 API Token（个人中心 → API keys）
2. 安装 CLI：`curl -fsSL https://skillhub.cn/install/install.sh | bash -s -- --cli-only`
3. 登录：`skillhub login --key <token> --host https://api.skillhub.cn`
4. 逐个预检：`skillhub publish <skill目录> --dry-run`（frontmatter 已含 slug/version/displayName，lint 已过）
5. 发布：`skillhub publish <skill目录> --changelog "首次发布"`

slug 已带 `guolei-` 前缀防全网撞名。license 当前为 CC-BY-NC-4.0（未定稿，公开发布前请确认）。

## 质量说明

- 每位专家经 8 条盲测（应触发/诱饵/跨专家混淆三类），六家 48 条 + 回炉复测全绿
- 行为纪律：单轮至多一个新问题；无该企业证据不下诊断；法律/税务/投资/心理不越界给具体意见
- 术语口径统一见 GLOSSARY.md；案例数字凡不可验证处均带「业内估算/教学案例」口径标注
