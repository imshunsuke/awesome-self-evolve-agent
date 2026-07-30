# Awesome Agent Skills and Harnesses

A curated reading list of **2026 papers and technical reports** on agent skills, harness engineering, and experience-driven agent improvement.

[中文版本](README_zh-CN.md)

## Scope

This list focuses on work that changes an agent's reusable procedures or runtime infrastructure without relying solely on model-weight updates:

- **Skills**: creation, distillation, optimization, retrieval, composition, diagnosis, and continual evolution.
- **Harnesses**: runtime code and interfaces that control context, tools, actions, feedback, memory, and execution.
- **Experience reuse**: turning execution traces and feedback into persistent skills or improved harnesses.

## Surveys and Conceptual Foundations

1. **[Self-Improving Agents in the Era of Experience: A Survey of Self- to Meta-Evolution](https://openreview.net/forum?id=IUltZSgLMm)**  
   Che Jiang et al. · **Survey / preprint** · June 2026  
   Organizes self-improving agents around experience infrastructure: harnesses collect experience, skills and memory preserve it, reinforcement learning consolidates it, and meta-agents decide what should evolve.

2. **[Externalization in LLM Agents: A Unified Review of Memory, Skills, Protocols and Harness Engineering](https://arxiv.org/abs/2604.08224)**  
   Chenyu Zhou et al. · **arXiv technical report** · April 2026  
   Explains agent progress as cognitive externalization: memory externalizes state, skills externalize procedures, protocols externalize interaction structure, and the harness coordinates them into a reliable runtime.

## Harness Engineering

3. **[AutoHarness: Improving LLM Agents by Automatically Synthesizing a Code Harness](https://arxiv.org/abs/2603.03329)**  
   Xinghua Lou et al. · **ICLR 2026 RSI Workshop Poster**  
   Lets an LLM iteratively synthesize executable guard and policy code from environment feedback. On TextArena games, the generated harness eliminates illegal actions and can even become the full policy.

4. **[Adapting the Interface, Not the Model: Runtime Harness Adaptation for Deterministic LLM Agents](https://arxiv.org/abs/2605.22166)**  
   Tianshi Xu et al. · **arXiv preprint** · May 2026  
   Introduces Life-Harness, which converts recurring interaction failures into reusable interventions for environment contracts, procedural guidance, action realization, and trajectory control while keeping the model frozen.

5. **[Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052)**  
   Yoonho Lee et al. · **arXiv preprint** · March 2026  
   Searches directly over harness code. An agentic proposer inspects the source, scores, and traces of all previous candidates through a filesystem, then proposes improved runtime implementations.

## From Experience to Skills

6. **[Meta Context Engineering via Agentic Skill Evolution](https://arxiv.org/abs/2601.21557)**  
   Haoran Ye et al. · **ICML 2026** · [Code](https://github.com/metaevo-ai/meta-context-engineering)  
   Replaces fixed context-engineering recipes with evolved skills. A meta-agent improves the procedure for building context, while a base agent executes that procedure to produce flexible context files and code.

7. **[From Raw Experience to Skill Consumption: A Systematic Study of Model-Generated Agent Skills](https://arxiv.org/abs/2605.23899)**  
   Zisu Huang et al. · **arXiv preprint** · May 2026  
   Studies the full lifecycle from experience generation to skill extraction and consumption. It shows that generated skills help on average but can cause negative transfer, and that a strong skill writer is not necessarily a strong skill user.

8. **[Trace2Skill: Distill Trajectory-Local Lessons into Transferable Agent Skills](https://arxiv.org/abs/2603.25158)**  
   Jingwei Ni et al. · **arXiv preprint** · March 2026  
   Uses parallel analysts to extract lessons from many execution traces and hierarchically merge them into one conflict-reduced skill directory, yielding skills that transfer across models and out-of-distribution tasks.

9. **[SkillOpt: Executive Strategy for Self-Evolving Agent Skills](https://arxiv.org/abs/2605.23904)**  
   Yifan Yang et al. · **arXiv preprint** · May 2026  
   Treats a skill document as trainable external state. Scored rollouts drive bounded text edits, and a held-out validation gate accepts only improvements, making skill evolution more controlled and reproducible.

10. **[SkillOpt-Lite: Better and Faster Agent Self-Evolution via One Line of Vibe](https://arxiv.org/abs/2607.03451)**  
    Yifei Shen et al. · **arXiv preprint** · July 2026 · [Project](https://evolvinglmms-lab.github.io/SkillOpt-Lite/)  
    Packages validation-gated skill optimization into a lightweight coding-agent loop. Its HarnessOpt variant expands the editable surface from a skill file to selected harness code.

## Skill Libraries, Retrieval, and Continual Evolution

11. **[SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234)**  
    Peng Xia et al. · **ICLR 2026 MemAgents Workshop Oral** · [Code](https://github.com/aiming-lab/SkillRL)  
    Distills trajectories into a hierarchical SkillBank, retrieves general and task-specific guidance, and recursively evolves the library alongside a reinforcement-learned policy.

12. **[SkillTracer: Structural Failure Attribution and Refinement of Agentic Skills in Long-Horizon Web Tasks](https://openreview.net/forum?id=OiyEjThGeZ)**  
    Yuyang Li et al. · **KDD 2026; ICLR 2026 MALGAI Workshop**  
    Represents composite skills as attributed plan graphs with verifiable transitions, allowing long-horizon failures to be localized to specific nodes and repaired without rewriting an entire workflow.

13. **[Graph-of-Skills: Dependency-Aware Structural Retrieval for Massive Agent Skills](https://arxiv.org/abs/2604.05333)**  
    Dawei Liu et al. · **Agent Skills '26 Poster** · [Code](https://github.com/davidliuk/graph-of-skills)  
    Builds a graph over skill packages and retrieves a compact bundle that includes relevant skills and their dependencies, reducing the cost and confusion caused by loading a large flat library.

14. **[SkillX: Automatically Constructing Skill Knowledge Bases for Agents](https://arxiv.org/abs/2604.04804)**  
    Chenxi Wang et al. · **ICML 2026 AI for Math Workshop** · [Code](https://github.com/zjunlp/SkillX)  
    Automatically constructs a plug-and-play, multi-level skill knowledge base through trajectory distillation, iterative refinement, and exploratory expansion, then transfers it to weaker agents.

15. **[Memento-Skills: Let Agents Design Agents](https://arxiv.org/abs/2603.18743)**  
    Huichi Zhou et al. · **arXiv preprint** · March 2026 · [Code](https://github.com/Memento-Teams/Memento-Skills)  
    Treats structured skills as persistent, editable memory. Its read-execute-reflect-write loop retrieves or creates skills, executes them, and repairs or expands the library from deployment experience.

## Status Legend

- **Conference / Workshop**: accepted or published in the named 2026 venue.
- **Preprint / Technical report**: publicly available manuscript without a confirmed archival main-conference publication in this list.
- A workshop acceptance is not presented as a main-conference acceptance.

## License

The curated metadata and original summaries in this repository are released under [CC BY 4.0](LICENSE). Copyright for linked papers remains with their respective authors and publishers.
