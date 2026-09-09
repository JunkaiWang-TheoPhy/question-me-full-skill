<div align="center">

🇺🇸 [English](README.md) | 🇨🇳 [中文](README.zh.md)

<h1>Question Me Full Skill</h1>

![可见性](https://img.shields.io/badge/visibility-public-brightgreen) ![许可证](https://img.shields.io/badge/license-Apache--2.0-blue) ![类型](https://img.shields.io/badge/type-Codex%20skill-6f42c1)

<img src="assets/question-me-mastery-bridge.png" alt="学习者通过提问、复习和迁移逐步走过理解之桥" width="100%">

</div>

## 引言

`Question Me Full` 把已经完成的 Agent 工作转化为有证据依据的批量测验和持久、私有的学习记录。它根据对话与项目证据重建任务过程、考察用户理解，并把有限的知识总结保存在 Codex 数据目录中，而不写入被考察的工程。

它和 `grilling` 的使用阶段不同：

- `grilling` 用于执行之前，让尚未解决的用户决策塑造计划；
- `question-me-full` 用于形成有意义的工作结果之后，此时回答可以依据真实证据判断，并跨多次考察保留项目学习记录。

## 掌握循环

```text
已完成的工作
      ↓
基于证据的掌握地图与临时答案键
      ↓
一批客观题
      ↓
统一批改并链接关键证据
      ↓
保存私有知识总结并清除临时答案
```

完整题面与答案键只在考察进行期间存在。正常完成、用户主动停止、切换到无关话题或发生无法恢复的中断时，Skill 会清除临时材料，只保留按日期组织的自然语言总结，包括覆盖范围、正确率、优势、薄弱点与未考察部分。

## 证据边界

这个 Skill 不考察隐藏的思维链、偶然的实现细节、缺乏支持的主张或从未向用户开放的信息。如果项目只有数值支持而没有证明，考试必须保留这条边界，不能把猜想按已确立事实判分。

答题本身不授权修改项目。当回答暴露出可能的项目错误时，Skill 只记录候选纠错；只有用户明确要求后，才切换到调查或修复。

## 仓库内容

- [SKILL.md](SKILL.md) 保存规范行为。
- [agents/openai.yaml](agents/openai.yaml) 保存 Codex 界面元数据。
- [evals/scenarios.md](evals/scenarios.md) 保存行为评测案例。
- [references/record-lifecycle.md](references/record-lifecycle.md) 规定私有记录与清理流程。

## 安装

将本仓库安装为 Codex Skill，或复制到已经配置的 skills 目录；需要保留项目级学习历史时调用 `$question-me-full`。快速变化的项目或一次性考察应使用独立的临时版 `$question-me`。

## 许可证

本仓库采用 [Apache License 2.0](LICENSE)。
