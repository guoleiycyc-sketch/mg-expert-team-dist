# 道行私董专家团 · mg-expert-team

![version](https://img.shields.io/badge/version-2.0.0-blue) ![skills](https://img.shields.io/badge/skills-7-green) ![platform](https://img.shields.io/badge/platform-agentskills.io%20compatible-orange) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-lightgrey)

一组对话式私董 skill：**企业主带着生意的困惑进来，一位私董官带六位幕僚开圆桌**——先把「增长没劲」这类模糊主诉磨成一个真问题（案题）、建立跨会话的案主档案，再由各透镜幕僚提问与反馈深挖，最后以「可量化 + 监督人 + 复查日」的行动承诺收口。幕僚只提问不给建议，给建议必以「如果我是你」开头；所有人都同意时，黑帽子幕僚必须不同意。越用越懂这家企业。

适用于 Claude Code、WorkBuddy 等任何支持 [agentskills.io](https://agentskills.io) 规范（SKILL.md + frontmatter）的 agent 环境。纯对话型 skill，不依赖任何专有工具调用。

## 专家团编制（私董官 + 六位幕僚）

| 角色 | 花名 | 管什么 | 代表工具 |
|---|---|---|---|
| **board-facilitator** 私董官 | 岳察秋 | 案前打磨、主持私董八 Phase、建案主档案、议题定向、承诺收口 | 真问题公式、差距二分、崩塌测试、倾听四层、承诺三件套 |
| **board-strategy** 战略幕僚 | 方致远 | 方向与定位 | 市场洞察四问、定位六问、三层业务链、必赢之战 |
| **board-model** 商业模式幕僚 | 盛意达 | 生意本身的设计 | 画布四问、用户铁三角、十大坑体检、微创新三动作 |
| **board-growth** 增长幕僚 | 曾长青 | 增长引擎 | 销售额公式剥洋葱、流程病诊断、VSM |
| **board-org** 组织幕僚 | 杨沃土 | 人与组织 | 杨三角（先查土壤再怪种子）、两本账、人才盘点 |
| **board-review** 复盘幕僚 | 史鉴今 | 经营节奏 | 复盘四步法、复盘会四大坑、数据三比+看结构 |
| **board-challenger** 黑帽子幕僚 | 邓不同 | 专职唱反调 | 事实缺口盘问、逻辑漏洞检验、反例搜寻、共识盲区挑战 |

公共资产：`GLOSSARY.md`（共享术语表，含私董会术语分组）、`INDEX.md`（幕僚名片 + 私董八 Phase 流程图 + 互链图 + 使用说明）。

## 快速开始

**方式一 · Plugin 安装（推荐，一条命令装齐私董官+六幕僚+版本化升级）**

```
/plugin marketplace add guoleiycyc-sketch/mg-expert-team-dist
/plugin install mg-expert-team@mg-expert-team
```

**方式二 · 手动复制**

```bash
git clone https://github.com/guoleiycyc-sketch/mg-expert-team-dist.git
cp -r mg-expert-team-dist/skills/board-* ~/.claude/skills/ && cp mg-expert-team-dist/GLOSSARY.md ~/.claude/skills/
# 注意：直接把整个仓库或 skills/ 文件夹放进 skill 目录会报「找不到 SKILL.md」——必须是 board-* 目录平铺
```

**方式三 · 单包安装（一包一 skill 的平台）**：见 Releases 中的七个 board-*.zip，zip 根即 SKILL.md

然后对 AI 说一句：**「帮我开一场私董会，盘盘我生意上最大的难题」**或**「我公司的生意最近增长没劲」**——board-facilitator 私董官会接手。也可点名幕僚（「让商业模式幕僚看看我这个生意」「帮我挑挑刺」）或续会（粘贴上次档案说「接着上次聊」）。

完整安装与使用说明见 [INSTALL.md](INSTALL.md)（含 WorkBuddy 等平台安装、SkillHub 发布步骤）。

## 行为纪律（与普通「AI 顾问」的区别）

- **幕僚之问只提问不给建议**——「给建议就是剥夺别人的思考权」；建议必以「如果我是你」开头
- **私董官不与幕僚抢问题**——全场自己的分析性追问至多 1-2 个
- **单轮只问一个问题**——不连环审讯
- **无证据不下判断**——结论必须指向该企业档案里的记录
- **「该不该裁掉销售总监」不直接答**——先用真问题公式磨案题
- **所有人都同意时，黑帽子必须不同意**——挑战事实与逻辑，对事不对人
- **问知识 ≠ 开私董会**——纯知识提问答完即止，不顺势开圆桌
- **执业边界**——法律/税务/投资/心理只转介不给意见
- **会话必收口**——承诺三件套缺一不散场，监督人只能选一位（人人负责就没人负责）；续会第一件事查上次承诺兑现

## 质量

v1.x 六件 48 条盲测（应触发 / 诱饵 / 跨专家混淆三类）+ 回炉复测全绿——裸 agent 基线 47/48 会连环问或直接甩答案，带 skill 后 48/48 单轮一问。v2.0.0 私董化换轨后盲测题库同步更新至 7 件 59 条（私董官新增私董会入口词用例、黑帽子幕僚全新 8 条），发布前按同口径复测。

## 目录结构

```
├── skills/                       # 私董官 + 六位幕僚（SKILL.md + test-prompts.json）
│   └── board-facilitator/        #   另含 ARCHIVE_TEMPLATE.md（案主档案模板）
│       └── references/           #       与 intake-form.md（案题打磨表）
├── GLOSSARY.md                   # 共享术语表（术语正文 + 私董会术语 + 口径警示）
├── INDEX.md                      # 幕僚名片 + 私董八 Phase 流程图 + 互链图 + 使用说明
├── INSTALL.md                    # 安装与使用说明（Claude Code / WorkBuddy / SkillHub）
├── LICENSE                       # CC-BY-NC-4.0
└── README.md
```

## 版本

- **v2.0.0**（2026-09-04）：私董化大版本——团名升级「道行私董专家团」，mg-* 六件全量改名 board-*（skill 目录/frontmatter name/slug 三处同步，旧 guolei-mg-* slug 作废）；五环节流程重构为私董八 Phase（案前打磨/案题陈述/幕僚之问/真问题重构/隔墙有耳/幕僚反馈三段式/承诺收口/送一朵小红花），新增真问题公式、倾听四层、「如果我是你」通道、监督人只能一位等私董纪律；新增第六位幕僚 board-challenger 黑帽子邓不同（专职唱反调）；术语全量换轨（案主/幕僚/私董官/圆桌/定向）；GLOSSARY 新增私董会术语分组；全部方法论资产（五步假设链/崩塌测试/差距二分/档案七章/红旗表/判据/剧本/案例/口径警示）原样保留为私董官与幕僚的工具
- **v1.2.0**（2026-09-04）：私董会引导融入——原 mg-lead 新增首场双路径（快诊直接开聊／深备先填《案题打磨引导表》，新附 references/案题打磨引导表.md）、「期待的专家画像」定向佐证、「成功的一天」愿景练习、收口四问（先选最触动您的专家为主线）与圆桌带数指引；GLOSSARY 引用补路径说明
- **v1.1.1**（2026-09-02）：Plugin 化——新增 .claude-plugin/plugin.json 与 marketplace.json，支持 /plugin 一条命令安装与版本化升级；新增六个单包 zip（一包一 skill 平台用）；README 补三种安装方式与层级陷阱提示
- **v1.1.0**（2026-09-02）：按 skill-creator 标准校准——六家 description 补防漏触发推力句（弱信号/无术语主诉也激活）
- **v1.0.2**（2026-09-02）：外发规范修正——frontmatter 去工程注释、段标题去蒸馏框架标签、交叉引用同步
- **v1.0.1**（2026-09-01）：首版发布（企业管理专家团，mg-* 六件）。

## License

[CC-BY-NC-4.0](LICENSE)（非商业署名使用；正式商用前请联系作者调整授权）
