# 模型、参考图与界面用法

核查日期：2026-10-27。日常按本文件工作，用户要求更新或实际功能不符时再核查对应官方资料。提示词写法见 [设计与压缩](prompting.md)。

## 模型与交付

优先沿用用户明确选择的 MJ / Niji 及版本；未指定时沿用已有上下文。完全没有模型信息时可暂按 MJ V8.2 组织文字并简短说明，不因此阻塞设计。二次元题材不自动等于 Niji，模型更新也不自动意味着审美更合适。

| 模型 | 本 Skill 的使用方式 |
| --- | --- |
| Midjourney V8.2 | 通过界面选择；需要人物图参考或换装时可用 Edit Model |
| Niji 7 | 通过界面选择；按 Niji 的画面描述和参考能力组织，不套用 MJ 专用功能 |
| 用户指定的其他版本 | 保留选择；涉及版本专用功能时核实，不默默升级 |

成品代码块只放英文描述，不放任何参数后缀、命令、URL、风格代码或权重语法。即使使用 Discord，也不因切换渠道自动恢复后缀；只有用户明确要求带参数命令时才另行适配。

来源：[Version](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)、[Niji 7 发布说明](https://nijijourney.com/blog/niji-7)。

## 三种图片用途

以下为 MJ 网页端名称；Niji 独立站或移动端入口以实际可用界面为准，不凭空承诺同名按钮。

| 用途 | 入口与作用 | 常见误用 |
| --- | --- | --- |
| 角色、物件或编辑依据 | MJ V8.2 的 `Attach to prompt`，由 Edit Model 使用 | 把该功能当成 Niji 也具备的角色锁定 |
| 风格参考 | `Style Reference`，引导媒介、线条、颜色、光线和纹理 | 用它锁定人物长相，或再叠一套相反的画风 |
| 内容与构图参考 | `Image Prompt`，引导主体、构图和颜色 | 忽视它可能带入原服装、背景和姿态 |

只希望保留人物时，不默认把角色图同时放进三种入口。附图说明讲清每张图的作用；用户没有提供风格图或有效代码时用文字表达，不虚构代码。

来源：[Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)、[Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)。

## MJ V8.2：角色图与换装

将人物图放入 `Attach to prompt`，最多四张。可以描述最终画面，也可以明确“保留脸部与发型，替换服装”等修改。多张图用可辨认的特征指代对象，避免含糊的“参考上图”。

保留身份与保留原装分开写。换装时只保留必要的标志，不同时要求复制原图全部内容。使用风格参考时，保留一句与参考一致的媒介或画风描述可能有帮助，不必长篇复述参考图。

**比例例外**：官方说明 Edit Model 倾向沿用第一张图的比例，默认宽高比设置不会自动应用。当前无参数约定下，不偷偷补比例后缀，也不承诺只调默认比例就必然生效。可建议使用接近目标比例的首张参考图，或在编辑器调整实际画布；文字中的“全身”“竖向构图”不能保证精确像素比例。

V8.2 不使用旧 Character Reference / Omni Reference；不套用旧质量参数和多重文字权重。Edit Model 结果不支持 Remix，也不与 Tile 组合；用户没有使用这些功能时不必主动展开说明。

来源：[Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)、[Version](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)。

## Niji 7：清楚描述想看到的画面

Niji 7 更按字面执行，默认画风偏线条和平面表现。不要把“精准但平淡”直接判断为分辨率问题。

- 需要背景就写地点或环境；需要更强层次就给出合适的光线或绘画表现。只有头像或留白立绘需求时，可以主动保留简单背景。
- 需要全身时写清完整人物和脚部入画，必要时补鞋履或地面接触；这些是构图线索，不是保证。
- 想要动画截图感，可尝试 `anime screenshot`；想要更浓的绘画感或体积，选择相应媒介与光线，不一口气叠加所有渲染词。
- Raw 会改变默认审美，不作为自动开启的画质增强项。想保留较强二次元感时先按用户原有模式工作。

Niji 7 不支持旧 Character Reference；不要移植 MJ V8.2 的 Edit Model 或 V7 的 Omni Reference。角色图可用 Image Prompt 提供内容线索，但它不是专用身份锁定；文字补充最重要的辨识特征。用户重视还原度时说明这个边界，不暗中换模型。

来源：[Niji 7 提示指南](https://nijijourney.com/blog/niji-7-prompting)、[Niji 7 发布说明](https://nijijourney.com/blog/niji-7)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)、[Omni Reference](https://docs.midjourney.com/hc/en-us/articles/36285124473997-Omni-Reference)。

## 界面设置只在必要时说明

保留用户已有设置。未知时不假定用户已经开启或关闭某项，也不把每次交付变成设置教程。以下是诊断方向，不是一套强制预设：

| 设置 | 何时值得调整或核对 |
| --- | --- |
| 模型与比例 | 模型要与参考方式兼容；比例配合主体和场景，Edit Model 注意上面的例外 |
| Stylization | 细节持续不遵循时可试降低；审美过于平淡时再试增加；不是越高越清晰 |
| Raw | 默认审美与目标冲突时再对照；保留用户满意的默认画风 |
| Variety / Chaos | 探索构图时可增加；对照提示词时保持一致，避免把随机差异误认成修改效果 |
| Personalization / Moodboards | 不同账户或同文异图时检查当前启用项；先保持一致，仅在怀疑它是干扰源时单独对照 |
| 参考图及影响强度 | 先确认图放对入口；强度只影响相应参考，不是全局画质开关 |
| 分辨率 / HD | 构图和画风满意后再考虑输出分辨率；不能修复错误人物关系或不合适的设计 |

不要假定每种参数在每个站点或模型都有界面控件。缺少控件时说明限制或采用可行的无参数方法，不为凑齐功能擅自输出后缀。Seed 不是必要步骤，更不是角色记忆。

附图说明示例：

> 将人物图放到 MJ 的 `Attach to prompt`；风格图放到 `Style Reference`。此次保留人物外观，改为旅行服。

不重复用户已经完成且本次无变化的设置。用户把图片发给 AI，不等于已经上传到生成界面。

来源：[Creating on Web](https://docs.midjourney.com/hc/en-us/articles/33390732264589-Creating-on-Web)、[Stylize](https://docs.midjourney.com/hc/en-us/articles/32196176868109-Stylize)、[Raw](https://docs.midjourney.com/hc/en-us/articles/32634113811853-Raw)、[Chaos / Variety](https://docs.midjourney.com/hc/en-us/articles/32099348346765-Chaos-Variety)、[Personalization](https://docs.midjourney.com/hc/en-us/articles/32433330574221-Personalization)、[Seeds](https://docs.midjourney.com/hc/en-us/articles/32604356340877-Seeds)。
