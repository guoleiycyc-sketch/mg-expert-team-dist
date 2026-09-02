# 企业管理专家团 · mg-expert-team

![version](https://img.shields.io/badge/version-1.1.0-blue) ![skills](https://img.shields.io/badge/skills-6-green) ![platform](https://img.shields.io/badge/platform-agentskills.io%20compatible-orange) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-lightgrey)

一组对话式咨询 skill：**企业家带着生意的困惑进来，六位各管一域的专家接诊**——先把「增长没劲」这类模糊主诉磨成一个真问题、建立跨会话的企业档案，再分诊给对口的领域专家深挖，最后以「可量化 + 跟进人 + 复查日」的行动承诺收口。越用越懂这家企业。

适用于 Claude Code、WorkBuddy 等任何支持 [agentskills.io](https://agentskills.io) 规范（SKILL.md + frontmatter）的 agent 环境。纯对话型 skill，不依赖任何专有工具调用。

## 专家团编制

| 专家 | 管什么 | 代表工具 |
|---|---|---|
| **mg-lead** 总控 | 接诊、磨真问题、建档、分诊、行动收口 | 问题聚焦法、差距二分、崩塌测试、承诺三件套 |
| **mg-strategy** 战略 | 方向与定位 | 市场洞察四问、定位六问、三层业务链、必赢之战 |
| **mg-model** 商业模式 | 生意本身的设计 | 画布四问、用户铁三角、十大坑体检、微创新三动作 |
| **mg-growth** 增长 | 增长引擎 | 销售额公式剥洋葱、流程病诊断、VSM |
| **mg-org** 组织 | 人与组织 | 杨三角（先查土壤再怪种子）、两本账、人才盘点 |
| **mg-review** 复盘 | 经营节奏 | 复盘四步法、复盘会四大坑、数据三比+看结构 |

公共资产：`GLOSSARY.md`（共享术语表）、`INDEX.md`（专家名片 + 分诊流程图 + 互链图 + 使用说明）。

## 快速开始

```bash
git clone <本仓库>
# Claude Code（用户级）：
cp -r skills/mg-* ~/.claude/skills/ && cp GLOSSARY.md ~/.claude/skills/
# 或项目级：复制到 <项目>/.claude/skills/
```

然后对 AI 说一句：**「我公司的生意最近增长没劲」**——mg-lead 会接诊。也可点名专家（「让商业模式专家看看我这个生意」）或续诊（粘贴上次档案说「接着上次聊」）。

完整安装与使用说明见 [INSTALL.md](INSTALL.md)（含 WorkBuddy 等平台安装、SkillHub 发布步骤）。

## 行为纪律（与普通「AI 顾问」的区别）

- **单轮只问一个问题**——不连环审讯
- **无证据不下诊断**——判断必须指向该企业档案里的记录
- **「该不该裁掉销售总监」不直接答**——先打磨问题本身
- **问知识 ≠ 看病**——纯知识提问答完即止，不顺势开问诊
- **执业边界**——法律/税务/投资/心理只转介不给意见
- **会话必收口**——行动承诺三件套缺一不散场；续诊第一件事查上次承诺兑现

## 质量

六专家 48 条盲测（应触发 / 诱饵 / 跨专家混淆三类）+ 回炉复测全绿——裸 agent 基线 47/48 会连环问或直接开方，带 skill 后 48/48 单轮一问。

## 目录结构

```
├── skills/                  # 六位专家（SKILL.md + test-prompts.json）
│   └── mg-lead/             #   另含 ARCHIVE_TEMPLATE.md（企业档案模板）
├── GLOSSARY.md              # 共享术语表（术语正文 + 口径警示）
├── INDEX.md                 # 专家名片 + 分诊流程图 + 互链图 + 使用说明
├── INSTALL.md               # 安装与使用说明（Claude Code / WorkBuddy / SkillHub）
├── LICENSE                  # CC-BY-NC-4.0
└── README.md
```

## 版本

- **v1.1.0**（2026-09-02）：按 skill-creator 标准校准——六家 description 补防漏触发推力句（弱信号/无术语主诉也激活）
- **v1.0.2**（2026-09-02）：外发规范修正——frontmatter 去工程注释、段标题去蒸馏框架标签、交叉引用同步
- **v1.0.1**（2026-09-01）：当前版本。

## License

[CC-BY-NC-4.0](LICENSE)（非商业署名使用；正式商用前请联系作者调整授权）
