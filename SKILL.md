---
name: reality-illustration-interaction
description: Use when creating a still image where a photographed real object becomes a functional part of a hand-drawn scene, with a visible physical connection between the two media. Do not use for an ordinary photo filter, a separate illustration beside a photo, or a product exploded view.
---

# 现实与手绘互动

把真实物件借给画中角色使用：画面必须有一块明确的摄影区域、一块明确的平面手绘区域，二者由一件真实物件或它的一部分跨界连接。读者缩小图片后，应先看出两种媒介，再看懂“现实中的什么，成了画里的什么”。只有接触、没有摄影与手绘的视觉反差，不算完成。

## 先判断输入

1. **照片编辑**：用户提供有权使用的原照片，生成端点确实接收图片。把原照片当作实物形状、材质、透视和光线的真源；先列出必须保留的区域。编辑后逐项检查这些区域。不能仅凭文字提示词声称保留了原图。
2. **文字生成**：没有原照片，或端点只接收文字。先设计一个新的摄影场景及留白，再让同一张生成图里出现手绘世界。交付时称“文字生成的现实×手绘概念图”，不称“原照片图生图”。
3. **风格参考**：只借用“摄影实物参与手绘故事”的构图逻辑；不要复制参考图的具体物件、角色、连接方式、文案或水印。

若原照片没有足够留白、接点被遮挡或实物形状不适合承担新角色，先建议裁切或换图。不要靠堆特效掩盖物理关系不成立。

## 设计一条可见的关系

先填五项，再写提示词：

| 项 | 要写清楚的内容 |
| --- | --- |
| 真实物件 | 一件主要物件；原照片中可见的形状、朝向、材质和所在区域 |
| 借给画里的角色 | 这件物品在手绘世界里充当什么；它的真实形状为什么适合这个角色 |
| 接点 | 手、绳、影子、折边、光束或路径具体接在哪里；从哪里延伸到哪里 |
| 手绘动作 | 1–3 个小角色正在做的一件事；动作必须用到真实物件 |
| 画面分区 | 摄影区、平面绘图区、明确的媒介边界以及标题留白；手机缩略图仍可读 |

物件的“新身份”必须通过轮廓或受力关系看得出来。优先一个主隐喻，避免同一张图里把杯子同时写成山、湖和月亮。画中人即使被拿掉，实物仍像实物；实物若被拿掉，手绘动作应失去支点。摄影背景不能侵入绘图区，绘制的山水或布景也不能长进摄影区。若整体读起来是一张真实微缩模型照片，或是实景上贴了小人，即使接点连续，也要重做。

写提示词前先画出关系的空间顺序：实物起点、进入手绘区的位置、承重或作用的接点、终点。桥、绳、梯等承重物要逐端落到画中可见的支撑面，不能只让一端接上；人物的脚、手与承重物相接处要对齐。手绘人物和布景应位于平面手绘区，只有执行跨界动作所需的线条或接触点可以越过边界。成图后按同一顺序逐点复查；提示词写了“接上”而图片没接上，仍判失败。

## 写生成提示词

根据输入模式写完整提示词，并明确图片输入的职责。下面的方括号都要替换成具体内容：

```text
Create one cohesive vertical editorial image, not two pictures placed together.
Input mode: [edit supplied photograph / generate a new photoreal scene from text].
Photographic truth: [describe the exact real object, perspective, material, light, location, and the photo regions that must stay unchanged; for text mode, describe the new photographic scene].
Visual transformation: the real [object and visible feature] functions as [one role] in a small hand-drawn world because [shape or physical reason]. Do not replace the real object with a drawing.
Contact geometry: trace the real object from [physical origin] across [media boundary] to [first illustrated support/contact point], then to [last illustrated support/contact point]. [Character's hand or foot] touches [precise point on real object]. Every load-bearing end meets visible illustrated ground or support; no floating gap. The contact must be continuous and visibly plausible.
Illustrated action: [one concrete action with 1–3 small characters]. Use [chosen medium: graphite / ink / colored pencil / restrained watercolor] with hand-made line variation.
Composition: photographic region [position and approximate share] has photographic depth and texture; drawn region [position and approximate share] is visibly flat paper or illustrated negative space, with no photographic room or landscape behind its characters. Keep drawn characters and scenery within the drawn region except the exact contact gesture. The boundary sits at [specific line/edge]; [one real object] crosses it at [specific point]. Reserve [location] as clean breathing room. The contrast between media must read at phone size.
Color and light: carry [one or two real-photo colors] into restrained illustration accents; keep one coherent light direction and shadow logic.
No text, captions, logos, watermark, unrelated decorative characters, duplicate objects, pasted-on clip-art, fake paper tear, unmotivated splashes, illustrated scenery inside the photographic region, or photoreal background inside the illustrated region.
```

照片编辑模式再补：`Preserve the source photograph's object identity, silhouette, viewpoint, texture, and unedited background. Change only the planned illustration area and the contact point.` 如果端点不支持局部遮罩，把“保持不变”当作待检验目标，不当作已经实现的保证。

文字生成模式再补：`Photographic and drawn regions must belong to the same scene and perspective. The photographic object must remain convincingly real; the drawing may occupy the reserved blank area.`

提示词只描述图中确实能画出的关系。不要求模型写长段中文；标题、图注和说明由后期排版。若必须内嵌文字，逐字给定并在成图后人工校对。

### 调用模型前的留痕门槛

每张案例先建一个案例文件，再调用图像模型。案例文件至少写入：

1. Skill 版本或当前 `SKILL.md` 的文件哈希、案例 ID、实际输入模式和素材来源；
2. 上面的五项关系表，特别标出摄影区、平面手绘区、媒介边界和跨界接点；
3. 所选画法，以及从本 Skill 模板填写出的**完整最终提示词**，可存于案例文件或由案例文件明确指向的独立提示词文件；
4. 计划调用的模型、质量和尺寸。

保存后重新读取文件，确认提示词与关系表一致，再把文件中的提示词原样提交给模型。临时想到的新物件、动作或限制，必须先写成案例文件的新版本，不能只加在工具调用里。模型调用失败也记录请求和错误；不能把未出图的请求算成案例。工具超时后先检查输出目录：只有能根据单一在途请求、生成时间和文件确认归属的图，才进入目视验收；无法确认归属就标记未出图，避免盲目重复提交。若使用他人已有提示词或早期探索图，标明它与当前 Skill 版本的关系，不追认成按新版流程生成。

## 可选画法

画法只决定手绘部分的质地，不改变上面的物理关系。需要具体色彩和适用场景时读 [画法与场景](references/styles.md)。默认从细铅笔线稿开始；选一种主画法，必要时只加一种轻量辅材。

## 连续故事中的角色一致性

若多张图讲同一个故事，先从已入选画面写一份角色卡：年龄段、身高差、发型、固定服饰色块、绘制媒介和必须保持的儿童或成人体态。每张案例的最终提示词都要原样写入这些可见锚点，再单独写本张动作。仅有文字输入时，这些锚点只能提高视觉连贯性，不能保证人物身份严格一致；不要声称使用了未传入的参考图。

逐图比较角色卡：人数、年龄体态、发型、衣服主色和绘制质地有明显漂移，就留在候选或失败区，不以故事文案解释为同一个人。角色动作仍须依赖本张实物的可见接点；不能为了固定人物而弱化摄影与手绘的跨界关系。修正角色或接点时，先保存新版本提示词，再调用模型。

## 试跑与修订

先跑一张低成本构图验证图。按顺序看：照片区和手绘区能否一眼区分；实物是否仍然真实且可辨认；接点是否连续且跨过媒介边界；小角色是否真的在使用实物；手机缩略图是否读得懂。

失败时一次只改一个问题：接点错，改接点坐标和动作；实物被画掉，强化保留区域或改用支持图像输入的编辑端点；照片与手绘混成一种媒介，明确边界与跨界物件，删除越界布景；画面像无关的上下拼接，重写跨界的绳、光、影或路径；细节太多，删小角色和装饰。记录每轮提示词与结果，不把多处同时变化写成单因素结论。

最终交付：关系设计表、输入模式与素材来源、调用前保存的可复制提示词、实际生成参数、成功图与必要的失败图、逐图验收结论。案例记录格式见 [案例与验收](references/case-checklist.md)。
