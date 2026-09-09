<div align="center">

🇺🇸 [English](README.md) | 🇨🇳 [中文](README.zh.md)

<h1>Question Me Skill</h1>

![可见性](https://img.shields.io/badge/visibility-public-brightgreen) ![许可证](https://img.shields.io/badge/license-Apache--2.0-blue) ![类型](https://img.shields.io/badge/type-Codex%20skill-6f42c1)

<img src="assets/question-me-mastery-bridge.png" alt="学习者通过提问、复习和迁移逐步走过理解之桥" width="100%">

</div>

## 引言

`Question Me` 将已经完成的 Agent 工作转化为一套基于证据的掌握循环。一个有意义的任务或项目阶段完成后，Agent 从对话、产物、差异、测试、来源、决策和剩余限制中重建真实过程，再检验用户能否解释机制、审计证据，并把学到的方法迁移到相邻问题。

它和 `grilling` 的使用阶段不同：

- `grilling` 用于执行之前，让尚未解决的用户决策塑造计划；
- `question-me` 用于形成有意义的工作结果之后，此时回答可以依据真实证据判断。

## 掌握循环

```text
已完成的工作
      ↓
基于证据的掌握地图
      ↓
一道高价值问题
      ↓
回答分类与最小关键缺口
      ↓
提示、重答、延迟复测与迁移
```

提示后立即给出正确答案，只代表发生了修正，并不代表已经稳定掌握。只有当用户能够重建因果链、区分当前方案与合理替代方案、把主张连接到证据，并在没有泄露答案的提示下将机制用于新问题时，才可以判定掌握。

## 证据边界

这个 Skill 不考察隐藏的思维链、偶然的实现细节、缺乏支持的主张或从未向用户开放的信息。如果项目只有数值支持而没有证明，考试必须保留这条边界，不能把猜想按已确立事实判分。

答题本身不授权修改项目。当回答暴露出可能的项目错误时，Skill 只记录候选纠错；只有用户明确要求后，才切换到调查或修复。

## 仓库内容

- [SKILL.md](SKILL.md) 保存规范行为。
- [agents/openai.yaml](agents/openai.yaml) 保存 Codex 界面元数据。
- [evals/scenarios.md](evals/scenarios.md) 保存行为评测案例。

## 安装

将本仓库安装为 Codex Skill，或复制到已经配置的 skills 目录，然后在完成有意义的工作后调用 `$question-me`。

## 许可证

本仓库采用 [Apache License 2.0](LICENSE)。
