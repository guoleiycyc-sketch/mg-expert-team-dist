# 道行私董专家团 · 安装与使用说明

> 版本 2.0.0（2026-09-04）｜七人编制：board-facilitator 私董官岳察秋 / board-strategy 战略幕僚方致远 / board-model 商业模式幕僚盛意达 / board-growth 增长幕僚曾长青 / board-org 组织幕僚杨沃土 / board-review 复盘幕僚史鉴今 / board-challenger 黑帽子幕僚邓不同

## 这是什么

一组对话式私董 skill：企业主（中小企业主/创业者）对自己的生意提出困惑，私董官接手——先案前打磨，把模糊主诉磨成一个真问题（案题）、建立案主档案，再主持六位幕僚的圆桌（幕僚之问只提问不给建议、反馈走三段式与「如果我是你」通道），最后以「可量化 + 监督人 + 复查日」的行动承诺收口。跨会话累积案主档案。

**适用平台**：任何支持 agentskills.io 规范（SKILL.md + frontmatter）的 agent 环境——Claude Code、WorkBuddy 等。纯对话型 skill，不依赖任何专有工具调用。

## 安装

### 方式一 · Claude Code Plugin（推荐）

```
/plugin marketplace add guoleiycyc-sketch/mg-expert-team-dist
/plugin install mg-expert-team@mg-expert-team
```

一条命令装齐私董官+六幕僚，支持版本化升级（/plugin update mg-expert-team）。

### 方式二 · 手动复制（Claude Code / 其他 agentskills.io 平台）
把 skills/ 下七个 board-* 目录平铺到平台 skill 目录（如 ~/.claude/skills/）。
⚠️ 不要把整个仓库或 skills/ 文件夹整个放进去——skill 目录的每个一级子目录必须直接含 SKILL.md，否则报「找不到 SKILL.md」。

### 方式三 · 单包上传（一包一 skill 的平台，如部分 WorkBuddy 部署）
用 Releases 里的七个 board-*.zip——zip 根就是 SKILL.md，逐个上传即可（各包已自带 GLOSSARY.md，可独立安装）。

> 从 v1.x（mg-*）升级：旧 mg-* 目录与 guolei-mg-* slug 已作废，删除旧目录后按上述方式重装 board-*；案主档案（咨询档案/*.md）格式兼容，可直接续用。

## 使用（四种开始方式）

1. **开一场私董会**（推荐第一次用）：对 AI 说「帮我开一场私董会，盘一盘我生意上最大的难题」——私董官 board-facilitator 会开场定调、磨案题、主持八 Phase 圆桌
2. **直接说困惑**：「我公司的生意增长没劲」「人留不住」「天天救火」——私董官同样先接手，聚焦问题、建档定向
3. **点名幕僚**：如「让商业模式幕僚看看我这个生意」「帮我挑挑刺」（黑帽子）
4. **续会**：把上次案主档案粘贴回来，说「接着上次聊」——私董官第一件事核对上次行动承诺的兑现情况

## 专家团编制

| 角色 | 管什么 |
|---|---|
| board-facilitator 私董官 | 案前打磨：磨案题 → 建案主档案 → 议题定向 → 主持八 Phase 圆桌 → 行动承诺收口（守流程护场域，全场自己的分析性追问至多 1-2 个） |
| board-strategy 战略幕僚 | 方向与定位：看不懂外面（市场洞察）、定不了里面（定位/必赢之战） |
| board-model 商业模式幕僚 | 生意设计：画布四问、关键假设、十大坑体检、微创新 |
| board-growth 增长幕僚 | 增长引擎：堵点拆解、流程病诊断、价值流图 |
| board-org 组织幕僚 | 人与组织：激励归因（先查土壤再怪种子）、人才盘点 |
| board-review 复盘幕僚 | 经营节奏：复盘四步法、复盘会四大坑、业绩结构拆解 |
| board-challenger 黑帽子幕僚 | 专职唱反调：事实缺口盘问、逻辑漏洞检验、反例搜寻、共识盲区挑战——所有人都同意时他必须不同意 |

## 发布到 SkillHub（可选）

1. 注册 skillhub.cn + 实名认证 + 创建 API Token（个人中心 → API keys）
2. 安装 CLI：`curl -fsSL https://skillhub.cn/install/install.sh | bash -s -- --cli-only`
3. 登录：`skillhub login --key <token> --host https://api.skillhub.cn`
4. 逐个预检：`skillhub publish <skill目录> --dry-run`（frontmatter 已含 slug/version/displayName，lint 已过）
5. 发布：`skillhub publish <skill目录> --changelog "v2.0.0 私董化"`

slug 已带 `guolei-` 前缀防全网撞名（v2.0.0 起 guolei-board-*；旧 guolei-mg-* 作废下线）。license 为 CC-BY-NC-4.0（禁止商用、署名转载）。

## 质量说明

- 七件 skill 共 59 条盲测题（应触发/诱饵/跨幕僚混淆三类）；v1.x 六件 48 条盲测+回炉复测全绿，v2.0.0 换轨题库发布前按同口径复测
- 行为纪律：单轮至多一个新问题；幕僚之问只提问不给建议，建议走「如果我是你」通道；无该企业证据不下判断；法律/税务/投资/心理不越界给具体意见
- 术语口径统一见 GLOSSARY.md（含私董会术语分组）；案例数字凡不可验证处均带「业内估算/教学案例」口径标注
