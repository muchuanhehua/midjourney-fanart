# 提示词设计与压缩

本文件负责把设计变成 MJ / Niji 的可见画面描述；功能兼容性见 [模型用法](midjourney.md)，研究依据见 [经验依据](evidence.md)。

## 长度：限制冗余，不限制必要设计

官方强调清楚、简洁，也允许用细节提高控制力；没有在本次查阅的资料中找到适用于所有当前模型的统一“最佳词数”。不要把旧版社区的 token 数字当成现行硬限制。

本 Skill 使用以下编辑软预算，按空格分隔的英文词粗估即可：

| 情境 | 起步范围 | 取舍重点 |
| --- | --- | --- |
| 简单肖像、风格试探、已有强参考图 | 20–40 词也可以 | 不为凑长度添加装饰 |
| 常规单人同人图 | 通常 40–80 词 | 身份、一个看点、必要的情境与画风 |
| 双人关系、复杂服装或场景 | 通常 60–100 词，可按需更长 | 写清归属关系，优先保留硬要求 |
| Edit Model 的局部修改 | 以最短清楚表达为准 | 保留什么、改哪里、目标是什么 |

超过约 100 词时先删重、合并和排序，再判断是否仍有必要。不要机械截断，不把 100 当作模型容量，更不以词数判断出图好坏。用户要求的细节确有必要时可以超出；若关系本身过于复杂，先做主构图，再局部编辑，通常比继续扩写更值得尝试。

## 先选信息，再组织语言

在内部区分三层信息，不必把过程表格交给用户：

- **必须成立**：用户明确要求、人物数量和身份、核心动作或关系、指定构图或关键系列标志。
- **支撑看点**：能让主题成立的服装轮廓、一个重要道具、环境线索、色光关系。
- **可让模型发挥**：次要饰件、背景小物、重复材质形容、看不见的服装部件。

常见组织顺序是“主体与景别 → 关键辨识和动作 → 主题设计与环境 → 画风和光色”，但不是强制句式，也不声称靠词序就能精确分配模型权重。用户最重视的内容应容易定位，属性跟着所属对象走。

角色辨识通常抓住 2–4 个高价值特征作为起点，例如发型轮廓、发色、独特饰件或非人特征；不是每张都要写满，也不是上限。优先写当前景别中看得见的细节；不能为了凑齐特征改变用户构图。

一个清楚的动作、一处明确的场景关系，往往比更多装饰更能定义画面。若用户明确要求复杂场景，不擅自改成单人白底像。

## 用画面语言，减少空话与冲突

| 常见问题 | 改写方向 |
| --- | --- |
| “高级、绝美、梦幻、史诗、极致精细”连续叠加 | 写出真正需要的材质、光源或色彩关系，如月光透过薄纱 |
| “masterpiece, best quality, 8k, ultra detailed”固定后缀 | 默认删除；特定细节确有作用时直接描述，不当通用画质开关 |
| “她经历了很多苦难，但此刻终于被理解” | 落实为视线、表情、姿态和人物距离 |
| 把 Stable Diffusion 的标签、括号权重、负面词包直接搬来 | 改成清楚的自然语言短句；不输出多重提示权重语法 |
| 同时要求特写脸部、全身鞋子清楚、巨大远景 | 按本次重点选择相容的景别和主体占比 |
| 同时指定 flat cel shading、油画厚涂、写实皮肤和 3D 渲染 | 确立主导体系；确有混合意图时分清各自作用 |
| “no clutter, no extra people, no bad hands”长串否定 | 正面描述目标，如单一主体、简洁背景、明确的手部动作；不把移除参数变成负面词堆积 |

不要为插画默认添加相机品牌、镜头规格或摄影术语；只有确实需要相应的透视、景深或摄影感时才用。不要把所有媒介混搭都判错，关键是用户目标和视觉作用是否明确。

一般生图不写“please create”“make sure”“保持原图所有特征”等给助手的指令；直接描述目标。Edit Model 是例外，可以明确写保留与修改。

角色名和作品名可作线索，不能代替辨识特征或参考图。引号只用于用户确实希望出现在画面里的文字；不要把整条提示词加引号。

## 用参考图分担信息

- 角色图负责提供外观依据，文字强调关键身份和本次变化；不逐项复述图片里所有可见内容。
- 风格图承担主要视觉语言时，文字聚焦内容，并只补少量相容的风格特征；Edit Model 可保留一句明确媒介或风格描述。
- 普通 Image Prompt 可能带入原构图、服装或颜色；换装受阻时检查参考方式，而不是反复加“exact same character”。
- 不把 Image Prompt 或 Style Reference 说成精确身份锁定；也不把每个失败都归因于描述太短。

## 成品示例

以下为自拟的写法示范，未做实际生成验证，不是固定主题或通用画风。

### Niji：保留看点的单人情境

设定是一名银发、红色发带的角色在雨夜车站赴约；这些外观来自本例设定，不是对某个原作角色的断言。

```text
Waist-up anime illustration of a young woman with a silver bob and a red ribbon, wearing a navy cape over a cream dress. She holds a closed umbrella and glances back with a shy smile on a rain-soaked station platform. Warm train windows glow behind her, crisp linework and soft cel shading.
```

短提示词仍保留动作、地点、景别和暖冷关系；不会因为压缩而只剩“美丽银发少女”。

### 双人：属性贴着对象写

```text
Anime illustration of two travelers sharing tea at a lantern-lit stall. On the left, a short-haired woman in a red cloak offers a cup to a tall man on the right, whose dark braid rests over a blue coat. They exchange amused smiles, waist-up framing, loose ink lines and muted watercolor washes.
```

明确人数、左右和动作归属，不追加无关的多人背景来稀释关系。

### MJ Edit Model：简短的换装指令

```text
Keep the woman's silver bob, red ribbon, and facial features. Replace her armor with a navy traveling cape over a cream dress. Show her waist-up at a rainy train station, holding a closed umbrella, in a softly shaded anime illustration.
```

仅在确实附上人物图并使用 Edit Model 时使用这种编辑句式。普通 Image Prompt 应改写为最终画面描述。

## 输出前做一次压缩

删掉任一短语时，检查是否会改变用户在乎的可见结果。不会改变的优先删；可能承担关键风格作用的词，不凭“抽象”二字一律删除。

最终只交付已填好、无参数的完整提示词。不要同时附送一串“可加关键词”让用户自行拼接。需要对照实验时，再交付两条只改变一个主要因素的完整版本。
