# Agent Skills 与 Harness 精选论文

这是一个聚焦 **2026 年 agent skills、harness engineering 与经验驱动型智能体自我改进**的精选阅读清单。

[English](README.md)

## 收录范围

- Skill 的生成、蒸馏、优化、检索、组合、诊断与持续演化。
- Harness 对上下文、工具、动作、反馈、记忆和执行流程的组织与优化。
- 把运行轨迹和反馈转化为可复用 skill 或更优 harness 的方法。

## 先理解两个概念

- **Skill** 是智能体可复用的“做事方法”，例如操作流程、规则、脚本和注意事项。
- **Harness** 是模型外部的运行系统，决定给模型看什么、能调用什么工具、如何执行动作、怎样反馈错误、何时停止。

可以简单理解为：skill 是“经验写成的操作手册”，harness 是“让模型按规则工作的整套工作台”。

## 一、综述与概念框架

1. **[Self-Improving Agents in the Era of Experience: A Survey of Self- to Meta-Evolution](https://openreview.net/forum?id=IUltZSgLMm)**  
   Che Jiang 等 · **综述 / 预印本** · 2026-06  
   从“经验如何被系统利用”出发梳理自我改进智能体：harness 负责产生和管理经验，skill 与 memory 负责保存经验，RL 将经验写入参数，meta-agent 决定系统下一步应该改哪里。

2. **[Externalization in LLM Agents: A Unified Review of Memory, Skills, Protocols and Harness Engineering](https://arxiv.org/abs/2604.08224)**  
   Chenyu Zhou 等 · **arXiv 技术报告** · 2026-04  
   用“能力外化”统一解释 agent 系统：memory 外化状态，skill 外化程序性知识，protocol 外化交互结构，harness 把这些部分协调成可靠的运行时。

## 二、Harness Engineering

3. **[AutoHarness: Improving LLM Agents by Automatically Synthesizing a Code Harness](https://arxiv.org/abs/2603.03329)**  
   Xinghua Lou 等 · **ICLR 2026 RSI Workshop Poster**  
   让 LLM 根据环境反馈迭代生成可执行的约束与策略代码。在 TextArena 游戏中，生成的 harness 能消除非法动作，极端情况下甚至直接成为完整策略。

4. **[Adapting the Interface, Not the Model: Runtime Harness Adaptation for Deterministic LLM Agents](https://arxiv.org/abs/2605.22166)**  
   Tianshi Xu 等 · **arXiv 预印本** · 2026-05  
   提出 Life-Harness：不更新模型，而是把反复出现的交互失败转化为环境契约、流程指导、动作修正和轨迹控制规则。

5. **[Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052)**  
   Yoonho Lee 等 · **arXiv 预印本** · 2026-03  
   直接搜索和优化 harness 代码。提案 agent 通过文件系统读取所有历史候选的源码、得分和执行轨迹，再提出新的运行时实现。

## 三、从经验生成和优化 Skill

6. **[Meta Context Engineering via Agentic Skill Evolution](https://arxiv.org/abs/2601.21557)**  
   Haoran Ye 等 · **ICML 2026** · [代码](https://github.com/metaevo-ai/meta-context-engineering)  
   不再人工固定“如何做上下文工程”，而是让 meta-agent 演化这套方法本身；base agent 再执行演化后的 skill，生成具体的上下文文件与代码。

7. **[From Raw Experience to Skill Consumption: A Systematic Study of Model-Generated Agent Skills](https://arxiv.org/abs/2605.23899)**  
   Zisu Huang 等 · **arXiv 预印本** · 2026-05  
   系统研究“经验生成—skill 提取—skill 使用”整个生命周期。论文发现自动生成的 skill 平均有效，但存在明显负迁移，而且善于写 skill 的模型不一定善于使用 skill。

8. **[Trace2Skill: Distill Trajectory-Local Lessons into Transferable Agent Skills](https://arxiv.org/abs/2603.25158)**  
   Jingwei Ni 等 · **arXiv 预印本** · 2026-03  
   用多个分析 agent 并行阅读大量执行轨迹，先提取局部经验，再分层合并为一套尽量无冲突的 skill 目录；得到的 skill 能跨模型和跨分布迁移。

9. **[SkillOpt: Executive Strategy for Self-Evolving Agent Skills](https://arxiv.org/abs/2605.23904)**  
   Yifan Yang 等 · **arXiv 预印本** · 2026-05  
   把 skill 文档看成冻结模型的“可训练外部状态”。优化器根据带分数的轨迹做有限的增删改，并通过独立验证集只保留真正提高性能的版本。

10. **[SkillOpt-Lite: Better and Faster Agent Self-Evolution via One Line of Vibe](https://arxiv.org/abs/2607.03451)**  
    Yifei Shen 等 · **arXiv 预印本** · 2026-07 · [项目页](https://evolvinglmms-lab.github.io/SkillOpt-Lite/)  
    把带验证门控的 skill 优化封装成轻量级 coding-agent 循环；其中 HarnessOpt 进一步允许修改受限范围内的 harness 代码。

## 四、Skill 库、检索与持续演化

11. **[SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234)**  
    Peng Xia 等 · **ICLR 2026 MemAgents Workshop Oral** · [代码](https://github.com/aiming-lab/SkillRL)  
    从轨迹中蒸馏分层 SkillBank，在执行时检索通用和任务专用经验，并让 skill 库与强化学习策略递归地共同演化。

12. **[SkillTracer: Structural Failure Attribution and Refinement of Agentic Skills in Long-Horizon Web Tasks](https://openreview.net/forum?id=OiyEjThGeZ)**  
    Yuyang Li 等 · **KDD 2026；ICLR 2026 MALGAI Workshop**  
    把复合 skill 表示成带属性、可验证的计划图，使长任务中的失败能够定位到具体节点，只修坏掉的局部，而不是推倒整个流程重写。

13. **[Graph-of-Skills: Dependency-Aware Structural Retrieval for Massive Agent Skills](https://arxiv.org/abs/2604.05333)**  
    Dawei Liu 等 · **Agent Skills '26 Poster** · [代码](https://github.com/davidliuk/graph-of-skills)  
    为大量 skill 建立依赖图，执行时只检索一个紧凑且依赖完整的 skill 组合，避免把整个技能库塞进上下文造成高成本和混乱。

14. **[SkillX: Automatically Constructing Skill Knowledge Bases for Agents](https://arxiv.org/abs/2604.04804)**  
    Chenxi Wang 等 · **ICML 2026 AI for Math Workshop** · [代码](https://github.com/zjunlp/SkillX)  
    通过轨迹蒸馏、迭代修订和主动扩展，自动建立多层级、可插拔的 skill 知识库，并把强 agent 的经验迁移给较弱 agent。

15. **[Memento-Skills: Let Agents Design Agents](https://arxiv.org/abs/2603.18743)**  
    Huichi Zhou 等 · **arXiv 预印本** · 2026-03 · [代码](https://github.com/Memento-Teams/Memento-Skills)  
    把结构化 skill 当作可持续读写的外部记忆，通过“读取—执行—反思—写回”循环，从部署经验中修复旧 skill 或创建新 skill。

## 状态说明

- 标注会议或 workshop：已在对应 2026 venue 接收或发表。
- 标注预印本或技术报告：当前清单中尚未确认正式主会归档版本。
- Workshop 接收不会写成主会接收。

## 版权

本仓库仅保存公开链接、元数据和原创摘要，不重新分发论文 PDF。整理内容采用 [CC BY 4.0](LICENSE)，论文版权归原作者与出版方所有。
