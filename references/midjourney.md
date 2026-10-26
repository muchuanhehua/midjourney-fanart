# Midjourney 定稿用法

定稿日期：2026-10-26。日常创作按本文件执行，后续版本和用法由用户发起更新。

## 模型选择

| 模型 | 使用方式 | 本 Skill 的选择规则 |
| --- | --- | --- |
| Midjourney V8.2 | `--v 8.2` | 默认模型；使用角色参考图时优先采用其 Edit Model |
| Niji 7 | `--niji 7` | 用户明确选择 Niji 时使用，单独组织参考方式 |

两者是不同模型线，每份提示词只选择其中一个。二次元题材本身不意味着必须切换 Niji。

V8.2 的角色参考由 Edit Model 承担，不混用旧版 `--cref`、`--cw`、`--oref` 或 `--ow`。V8.2 不使用 `--q`，也不使用 `::` 多重文字提示词权重语法。

来源：[Version](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)。

## 三种图片用途

| 用途 | 网页端位置 | 负责什么 |
| --- | --- | --- |
| 角色或物件参考 | V8.2 的 `Attach to prompt` | 以图片为依据生成或改造人物、物件 |
| 风格参考 | `Style Reference` | 借鉴线条、色彩、媒介、纹理等视觉语言 |
| 内容与构图参考 | `Image Prompt` | 引导主体、画面安排、颜色等整体内容 |

同一张图片可以承担不同用途，但应按本次需要选择。用户只希望保留人物时，不把角色图默认同时设为风格与构图参考。

来源：[Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)、[Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)。

## V8.2：角色图与换装

网页端将用户提供的角色图上传到 `Attach to prompt`，最多四张。提示词可明确说明保留哪些人物特征，以及服装、姿势和场景如何改变。参考多张图时，用清楚的外观描述指代各对象，避免含糊的“参考上图”。

例如，换装任务应说明保留脸部、发型和标志性饰件，并将原服装改为指定主题服装；不要同时要求保留完整原装。参考图提供人物依据，文字仍应交代本次画面。

Edit Model 支持描述目标画面，也接受明确的修改指令。它会倾向采用第一张图的比例，指定输出比例时显式写 `--ar`。结果不支持 Remix，也不与 `--tile` 组合。

中文使用说明保持简短，例如：

> 请将角色图放入 `Attach to prompt`。保留人物外观，服装和场景按提示词改造；输出比例 2:3。

用户把图片发给 AI，不等于已经上传到 Midjourney。

来源：[Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)。

## 风格参考

网页端把风格图放入 `Style Reference`；Discord 使用 `--sref` 接真实图片 URL，或接用户已提供的有效风格代码。没有参考图或代码时，直接用文字表达风格，不编造代码。

`--sw` 控制风格参考强度，范围 0–1000，官方默认值为 100。仅在使用风格参考时考虑调整，不把它当作全部绘画风格的总开关。文案与参考图应互相配合，避免加入冲突的媒介和渲染要求。

来源：[Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)。

## Niji 7 分支

使用 `--niji 7`；不同时附加 `--v 8.2`。需要背景、具体景别或明暗层次时直接描述，避免只给人物与宽泛情绪词。`--raw`、`--sref` 和 Chaos 可以用于该模型。

Niji 7 不支持旧 `--cref`；本定稿也不把 V8.2 的 Edit Model 或 V7 的 Omni Reference 参数移植到 Niji。用户提供的角色图可以作为 Image Prompt 引导内容，但不将它描述为精确锁定身份的专用功能。Image Prompt 的 `--iw` 范围为 0–2，默认 1，只有明确需要调整普通图像提示的影响时才使用。

用户选择 Niji 且重视身份还原时，说明采用的参考途径及其用途；不暗中切换模型。文字应补充最关键的辨识特征。

来源：[Niji 7 发布说明](https://nijijourney.com/blog/niji-7)、[Niji 7 提示指南](https://nijijourney.com/blog/niji-7-prompting)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)。

## 常用参数与选择

参数放在文字描述之后，以空格分隔，使用两个英文连字符。每份成品只保留本次有用的参数，不自动堆满参数表。

| 参数 | 用途与范围 | 创作时如何选择 |
| --- | --- | --- |
| `--ar W:H` | 宽高比例，整数比例 | 按用途和构图选择；角色竖图可用 2:3，头像可用 1:1，横向场景可用 3:2 |
| `--s N` | Stylize，0–1000，默认 100 | 控制模型自身的审美发挥；先用默认值，需要更贴合具体描述时再考虑降低 |
| `--raw` | 减少模型默认审美干预 | 需要更直接执行文字风格或修改指令时考虑使用，不作为固定画质后缀 |
| `--c N` | Chaos，0–100，默认 0 | 确定系列方案时可保留默认值；探索更多差异时再提高 |
| `--no ...` | 排除不想出现的元素 | 只列必要对象；复杂否定改成正面描述所需画面 |
| `--seed N` | 控制生成的起始随机状态 | 仅在比较改动时按需保留，不作为保存角色或风格的方法 |
| `--hd` | V8.2 的高分辨率选项，可与 Edit Model 使用 | 用户需要高清输出时添加，不默认增加生成开销 |

`--no` 会分别理解其中的词，避免用长短语承担复杂逻辑。Seed 不能代替角色图、风格图或清晰的设计规则。

来源：[Parameters](https://docs.midjourney.com/hc/en-us/articles/32859204029709-Parameter-List)、[Aspect Ratio](https://docs.midjourney.com/hc/en-us/articles/31894244298125-Aspect-Ratio)、[Stylize](https://docs.midjourney.com/hc/en-us/articles/32196176868109-Stylize)、[Raw](https://docs.midjourney.com/hc/en-us/articles/32634113811853-Raw)、[Chaos](https://docs.midjourney.com/hc/en-us/articles/32099348346765-Chaos-Variety)、[No](https://docs.midjourney.com/hc/en-us/articles/32173351982093-No)、[Seeds](https://docs.midjourney.com/hc/en-us/articles/32604356340877-Seeds)。

## 网页端与 Discord 的交付差别

默认按网页端交付，用户可直接上传图片；英文提示词不需要虚构 URL。首次出现会影响交付的渠道差异时，可以简短说明默认网页端，用户另有选择则适配。

Discord 中，Edit Model 使用 `--edit` 后接真实图片 URL，多图以空格分开；风格图使用 `--sref` 后接真实图片 URL；普通 Image Prompt 的 URL 放在文字描述前。`/imagine` 是 Discord 命令入口，不放入网页端提示词。

需要 URL 却尚未获得时，交付已完成的文字部分并明确说明缺少图片 URL，或提供网页端使用方法；含占位符的结构示意不能标成可直接使用的最终命令。

来源：[Edit Model](https://docs.midjourney.com/hc/en-us/articles/48495453462797-Edit-Model)、[Style Reference](https://docs.midjourney.com/hc/en-us/articles/32180011136653-Style-Reference)、[Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)。

## 提示词表达

一般文字生图与 Image Prompt 描述想看到的画面；Edit Model 可以同时明确保留与修改事项。以人物身份、主题设计和核心动作为重点，再安排环境、构图和风格。描述有意义的可见细节，不用长篇解释创作意图。

角色名与作品名可作为文字线索，但不代替参考图。图中看不清的细节不自行断言为原作设定。只有用户确实要求画面中的文字时才指定字样，不添加说明性标题或模板变量名。

来源：[Prompt Basics](https://docs.midjourney.com/hc/en-us/articles/32023408776205-Prompt-Basics)。
