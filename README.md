# nkj-skills

NikelChieh 自建的 [Claude Code](https://docs.claude.com/en/docs/claude-code) skill 合集。

每个 skill 独立成 plugin，可按需逐个安装，互不影响。

---

## 安装

### 1. 添加 marketplace（一次即可）

在 Claude Code 中执行：

```
/plugin marketplace add NikelChieh/nkj-skills
```

> 这会把本仓库注册为可用的 marketplace，但不会安装任何 skill。

### 2. 按需安装单个 skill

```
/plugin install design-checklist@nkj-skills
```

想装哪个就装哪个。要列出 marketplace 里有哪些 plugin：

```
/plugin marketplace list nkj-skills
```

### 3. 更新 / 卸载

```
/plugin update design-checklist@nkj-skills      # 更新单个
/plugin uninstall design-checklist@nkj-skills   # 卸载单个
/plugin marketplace update nkj-skills           # 拉取 marketplace 的最新元数据
```

---

## 可用 Skills

| Skill | 简介 | 安装命令 |
|---|---|---|
| [`design-checklist`](./design-checklist/) | 针对研究 / 实验 / 技术方案，生成结构化核心问题清单（设计决策分析） | `/plugin install design-checklist@nkj-skills` |

---

## 各 Skill 详细说明

### `design-checklist`

**用途**：在动手做实验、写代码、启动新项目之前，先把所有关键设计决策列清楚——每个决策点都要有候选方案、优缺点对比、明确建议，最后还附上可执行的实验流程规划。

**适用场景**：
- 开始一个新研究 / 实验前
- 评估技术选型时（例如选 embedding 模型、选数据库、选框架）
- 系统设计 review 前的准备工作
- 任何你想"在动手前先想清楚"的时刻

**用法**：

```
/design-checklist 为 RAG 系统选择 embedding 模型
```

或者不带参数，让 skill 从当前对话上下文推断主题：

```
/design-checklist
```

**输出结构**（节选）：
- 3–6 个核心决策问题，每个含背景、候选方案对比表、明确建议
- 末尾附实验流程规划（基于推荐方案）
- 全程中文，术语保留英文

---

## 仓库结构

```
nkj-skills/
├── .claude-plugin/
│   └── marketplace.json          # marketplace 元数据，列出所有可装 plugin
├── design-checklist/             # plugin 1（每个 plugin 独立目录）
│   ├── .claude-plugin/
│   │   └── plugin.json
│   └── skills/design-checklist/
│       └── SKILL.md              # 真正的 skill 内容
└── README.md
```

新增 skill 时，复制一个 plugin 目录改名，更新 `marketplace.json` 的 `plugins` 数组即可。

---

## License

MIT
