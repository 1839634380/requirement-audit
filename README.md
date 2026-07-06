# Requirement Audit Skill

用于根据需求文档审查游戏项目的需求完成度、潜在 Bug 风险和游戏内表现。

## 适用场景

- 根据需求文档核查项目实现情况
- 检查功能是否形成闭环
- 分析已实现功能的潜在 Bug
- 输出 QA 可用审查报告

## 安装

将整个 `requirement-audit` 文件夹放入 Codex 的 skills 目录：

```
~/.codex/skills/requirement-audit/
```

## 输入

- 需求文档（.md/.txt/.docx 路径或直接粘贴内容）
- 项目路径
- 项目类型（如 UE5、Unity 等）
- 检查范围（可选，指定模块/文件）

## 输出

- 原子需求点拆解
- 对应代码/蓝图/资源证据
- 完成度判定（已完成/疑似已完成/部分完成/未完成/无法验证）
- 潜在 Bug 风险及游戏内表现推演
- QA 测试建议

## 使用示例

```
使用 requirement-audit 审查 F:\ls4\trunk 中 M1.1.4 版本的需求完成度，
需求文档路径为 D:\docs\M1.1.4.md
```

## 文件结构

```
requirement-audit/
├── SKILL.md                       # 核心工作流
├── agents/openai.yaml             # UI 元数据
├── references/
│   ├── completion_rules.md        # 完成度判定规则
│   ├── bug_risk_rules.md          # Bug 风险检查清单
│   └── report_template.md         # 审查报告模板
└── README.md
```

## 核心原则

1. 没有证据证明完成 → 不能判定为已完成
2. 没有明确反证证明没做 → 不能判定为未完成
3. 证据不足时 → 优先判定为疑似已完成或无法验证