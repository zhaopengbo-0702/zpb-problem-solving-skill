# zpb-problem-solving-skill

一个面向基础薄弱、但希望真正理解题目的学习者的通用讲题 skill。把“耐心讲清楚”落实为七步教学流程，适用于数学、物理、算法及其他需要推导的课程题。

它封装的是**如何讲解与解答题目**，不包含某一道题的具体答案。

## 七步讲题方法

1. **整体地图与思路来源**：用大白话翻译题意，给出解题路线，解释为什么会想到每一步。
2. **知识体系**：严格陈述实际用到的主干知识，再用生活类比、小例子解释，并推导二级结论、三级推论。
3. **考场流程**：总结“看到什么 → 想到什么 → 写下什么 → 怎样继续”的操作顺序。
4. **易错点**：定位错误发生的步骤，解释原因，给出修正办法。
5. **原题规范解答**：逐小问先讲通俗思路，再给完整证明或计算，重要公式独立居中。
6. **考试策略**：结合明确的考试情境分配时间，说明卡点后的可行路线与快速验算方法。
7. **深入拓展**：三种常见变形、主要多解及优劣、同类题的构造思路、至少五个有实质联系的跨领域应用。

准确性优先：不静默修改题意，不用类比代替证明，不伪造评分规则，不为凑数量编造跨领域关系。术语首次出现时解释，正常渲染数学符号，不把数学文本放进代码块。

## 在 Codex 中安装

需要 Git。将仓库克隆到个人 skills 目录。

Windows PowerShell：

```powershell
git clone https://github.com/zhaopengbo-0702/zpb-problem-solving-skill.git "$env:USERPROFILE\.codex\skills\zpb-problem-solving-skill"
```

macOS / Linux：

```sh
git clone https://github.com/zhaopengbo-0702/zpb-problem-solving-skill.git ~/.codex/skills/zpb-problem-solving-skill
```

如果设置了自定义 CODEX_HOME，请安装到该目录的 skills 子目录。目标目录已存在时，先检查其内容，不覆盖自己的改动。安装后重新打开 Codex 或开始新会话，让客户端重新发现技能。

更新已通过 Git 安装的副本：在该副本目录中运行以下命令；若有本地改动或分支分歧，先检查并处理，命令不会强制覆盖它们。

```sh
git pull --ff-only
```

## 调用示例

完整讲题：

```text
请使用 $zpb-problem-solving-skill，按七步从零基础讲透下面的题目。
解释思路从哪里来，每一小问完整推导，并讲常见变形和考场策略。
题目：在这里提供题干。
```

只讲某一部分：

```text
请使用 $zpb-problem-solving-skill，这次只讲第一个思路为什么会想到，先不要给最终答案。
```

默认允许自动匹配适用的讲题请求，也可以显式调用。用户最新要求可以缩小讲解范围，七步结构不会强制覆盖“只要提示”等明确指令。

## 文件结构

```text
zpb-problem-solving-skill/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   └── depth-and-transfer.md
├── evals/
│   └── cases.md
└── README.md
```

- SKILL.md：技能入口、七步流程及输出自查。
- agents/openai.yaml：Codex 展示名称、默认提示及自动调用设置。
- references/depth-and-transfer.md：需要深入拓展时按需读取的教学准则。
- evals/cases.md：人工或独立代理可使用的行为验收案例，不是自动评分程序。

该 skill 本身不要求安装 Python、调用外部模型 API 或执行任何上传操作。具体题目如需计算或查证，使用当前环境已有的适当工具。
