# 经验依据与适用边界

核查日期：2026-10-27。供维护 Skill、解释取舍和更新资料时读取；普通创作不必重读全部来源。

## 官方资料支持的结论

| 结论 | 来源与适用边界 |
| --- | --- |
| 提示词应简洁、具体；短提示词留出发挥空间，关键细节需要明说 | [MJ Prompt Basics](https://docs.midjourney.com/hc/en-us/articles/32023408776205-Prompt-Basics)。支持压缩冗余，不支持“所有模型越短越好” |
| Niji 7 更按字面执行，默认画风较平，想要背景、景别和明暗需明确描述 | [Niji 7 Prompting Guide](https://nijijourney.com/blog/niji-7-prompting)、[Niji 7 发布说明](https://nijijourney.com/blog/niji-7)。长一些但内容明确的提示词也有价值；描述鞋子只是可尝试的全身构图线索，不保证成功 |
| 风格参考不等于角色参考；文字应简洁并与参考画风相容 | [Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)。有参考图时不应叠加冲突的风格词 |
| 普通 Image Prompt 引导内容、构图和颜色；文字描述最终画面 | [Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)。不能承诺精确复制身份 |
| Edit Model 接受修改指令；参考图与功能有模型兼容边界，默认宽高比设置不会自动应用 | [Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)、[Version](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)。不能把“保留并替换”的写法套给所有参考方式 |
| Stylize、Raw 和个性化改变模型如何解释画面，不是无条件提高质量 | [Stylize](https://docs.midjourney.com/hc/en-us/articles/32196176868109-Stylize)、[Raw](https://docs.midjourney.com/hc/en-us/articles/32634113811853-Raw)、[Personalization](https://docs.midjourney.com/hc/en-us/articles/32433330574221-Personalization) |
| Seed 有助于比较，但不能保存角色或风格，也不能消除所有生成差异 | [Seeds](https://docs.midjourney.com/hc/en-us/articles/32604356340877-Seeds)。不将固定 Seed 作为无参数工作流的必要步骤 |

## 社区一手案例提供的启发

社区帖只作为作者报告或探索线索，不视为受控实验、模型机制证明或普遍结论；未逐张独立验证帖子中的出图效果。

- [What am i doing wrong](https://www.reddit.com/r/midjourney/comments/1s7cvxf/what_am_i_doing_wrong/)（2026-03-30）：作者报告长短提示词都未得到想要的花田远景，讨论同时涉及景别、宽高比和花朵密度的归属。启发：诊断应核对画面语义与构图，不能只数词数；不采纳帖中“LLM 一定不会写提示词”等绝对判断。
- [the quality gap between Niji 7 and Niji 6](https://www.reddit.com/r/midjourney/comments/1qi702u/the_quality_gap_between_niji_7_and_niji_6/)（2026-01-20）：作者报告同一提示词换版本后更不喜欢结果，评论对细节正确与风格满意的评价并不一致。启发：审美匹配与提示遵循分开诊断；无法由个例证明某一版本质量普遍更差。
- [Same prompt various srefs outputs](https://www.reddit.com/r/midjourney/comments/1j7w527/same_prompt_various_srefs_outputs/)（2025-03-10，Niji 6）：作者列出相同正文配不同风格代码的结果。启发：比较时要记录参考设置，正文不是唯一变量；不照抄旧版代码，也不保证在新模型复现。

## 本 Skill 的编辑约定，不冒充官方结论

- 纯提示词不带参数是用户工作流约束，不能解释成“参数有害”。需要调整的设置在代码块外说明。
- 40–80 词起步、超过约 100 词审查，是减少 LLM 扩写和方便人工比较的软预算；没有证据证明它是 MJ / Niji 的普遍最优区间。
- 少量高价值身份特征、一个主导视觉看点、有限风格特征，以及先重写再合成模板，都是编辑方法，需由返图检验。
- 不采纳跨版本通用的“超过 75 token 就无效”、固定位置精确权重、堆画质词必定提升质量等未经当前资料证实的说法。
- 不把“新模型更准确”等同于“更符合用户审美”，也不因社区个例默认换模型。

## 验证与更新

本次修改依据官方资料、社区作者报告和静态提示词审查，未进行 MJ / Niji 实际生图。当前“质量差”的具体原因仍需结合用户原提示词、设置与返图定位。

实际验证按 [反馈迭代规则](feedback.md) 固定模型、附图和设置，比较少量明确差异。只有用户认可且有相应返图支持，才把尝试标成已验证。用户要求更新或遇到实际兼容问题时重新核查相关来源；不能把此核查日期当作后续功能的保证。
