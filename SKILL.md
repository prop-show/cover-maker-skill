---
name: artifact-template-propshow-paper-covers
description: "Create an image using the PropShow Paper Covers template and its retained reference file. Use when the user selects this template, names PropShow Paper Covers, or explicitly invokes $artifact-template-propshow-paper-covers. 生成以葵为主角的 PropShow 纸艺拼贴视频封面，按题材变化配色和构图，默认分别生成 16:9 横版与 4:3 两张独立构图的正式封面。"
---

# PropShow Paper Covers

Create an image from this template. Keep the reference file unchanged.

## Workflow

1. Read `artifact-template.json` and resolve its paths relative to this skill directory.
2. Invoke $imagegen with the retained PNG as a reference image and the user's requested content as the edit or generation brief.
3. Treat the user's prompt and available sources as the content input. Do not invent factual claims merely to fill the composition.
4. Preserve the reference's visual language unless the user explicitly requests a deviation.
5. Visually inspect the generated image for fidelity and defects, then return the final image.

## Fidelity

Preserve the paper material, character identity, visual hierarchy and shared lighting. Vary palette and composition by topic as specified below; the retained example is not a fixed layout.

User instructions control requested content and explicit deviations. The retained reference anchors material quality, not a mandatory palette or pose.

## PropShow 纸艺封面约定

适用于 PropShow 视频封面和同系列测试图。默认每期交付两张独立成品：16:9 横版和 4:3 版，各自构图；用户明确只要一种比例时遵从该要求。只有用户要求主页模拟或对比表时才把多张封面排在一幅图里，不把双版本拼成一张代替两个文件。用户提供主题、标题或视频链接即可，不要求填写参数表。生成请求直接执行；仅要求 prompt 时只交付提示词。

### 角色和素材

- 读取本目录的 `assets/aoi.webp` 和 `references/aoi-identity.md`；生图前逐张查看图片。
- 图片输入顺序固定为 Image 1 — 葵 identity reference only，Image 2 — `assets/reference.png` paper material reference only。需要系列整体参考时再附 `assets/series-reference.png`，明确不得生成整页或照抄同一姿势。
- 葵必须参与核心动作；保留银灰碎发、低双马尾、薄荷发尾、绿眼、角色左侧的黑色薄荷 `<>` 发夹、炭黑敞开连帽衫和白色 `>_` T 恤。不能混入旧版贝雷帽或裙装。角色与道具共享纸张材质、投影和笔触。
- 自包含角色资产是创建时的批准快照；用户明确更新身份时，再以其新批准素材更新，不静默覆盖其他角色库。

### 统一材质，不固定模板

- 核心语言：纤维纸面、剪纸或撕纸边缘、克制的叠层和同方向浅投影。精细动漫五官可保留，人物衣服和道具应融入纸艺。
- 题材决定配色、构图、人物大小与表情。参考图的浅蓝与杏橙配色、左字右人布局不应成为所有视频的默认。
- 通常一个核心动作、2–4 个必要道具、2–4 个主色，背景大面积安静。避免满屏碎纸、漫画速度线、闪电、粒子和装饰性小字。
- 技术工具可用深青底与米白标题；组件可用淡紫/薄荷；Mac 工具可用奶黄与藏蓝；安全主题可用杏橙/赭黄；这些只是参考，非绑定的分类色。
- 同一批至少变化标题位置、人物尺度或动作之一，不机械重复“左字右人”。

### 事实与文案

- 从用户标题、链接正文、视频说明中确认主题。无法播放视频时，明确依据可读标题/说明，不声称完整观看。
- 标题提炼为 4–8 个汉字和一个必要产品名。保留产品拼写。封面抓主题，推荐的视频标题交代具体内容，避免完全重复。
- 不编造提速倍数、兼容性、保证安全、功能、日期、版本或点击率提升；产品标志按下面的官方 Logo 规则处理；不要把中性道具图案包装成产品标志。
- 默认小号 PropShow 品牌字；不要把自行重画的图案宣称为官方频道 logo。

### 官方产品 Logo

- 视频提到具体产品、框架或库时，先查其官网品牌页、官方文档站或官方仓库的 Logo 素材；找到可靠素材后，在封面合适位置加入该官方 Logo 的纸艺化变体。
- 记录产品名、官方来源页、素材 URL 和本地素材路径；先查看真实素材，再作为图像参考附在角色原图和纸艺参考之后，逐张标明对应产品。
- 可改变为剪纸、叠纸、压印或浅投影，但保留核心轮廓、结构、比例、方向和主要识别色；遵守来源给出的品牌使用要求。不得只靠文字提示让模型凭记忆重画，也不能把相似图标或自行设计的符号当成官方 Logo。
- Logo 可成为标题旁小标记、道具表面图案或场景中的品牌元素，不强制放在角落，不喧宾夺主。同一期双比例使用相同素材与变体语言。
- 多产品比较时分别读取、注入各自官方素材，避免互换或混合。无独立产品身份的通用概念（如 CRUD、fetch、API）无需硬找 Logo。
- 无法取得可核验官方素材时，只保留产品文字并说明缺失；不编造 Logo，不以第三方聚合站的近似标志冒充官方来源。
- 验收额外核对 Logo 与源图是否一致；如果生成结果扭曲核心特征，做定向修正，未通过的版本不可标记为已验收。

### 16:9 与 4:3 独立构图

- 默认每期生成两个独立文件：完整不透明的 16:9 横版和 4:3 版，分别设计标题、人物与道具的比例和位置。
- 16:9 充分使用横向空间，可使用横向叙事、左右对拉等布局；不再把主要内容强制压入中央 4:3，不额外保留左右各 12.5% 的裁切空白。
- 4:3 围绕较紧凑的画幅重新排版，可调整标题换行、人物尺度、动作朝向和道具分布；不能直接裁切、拉伸、加边或挤压横版作为正式版本。
- 同期两版保持标题文字、产品名、主色、角色身份和核心主题动作一致；换行、视角和布局可适配画幅，不能变成两套无关设计。
- 两张都各自避开画布边缘、底部和右下角的常见信息遮挡位置。关键文字、脸部与重要手势保留适当余量；这不等于要求 16:9 兼容中央 4:3 裁切。
- 先生成并检查一版，再生成另一版。每次都附上角色原图与纸艺参考；可将先生成的批准成品作为第三张一致性参考，明确只继承内容与风格，重新构图而非裁切。
- 分别查看实际像素尺寸，确认各自比例；分别检查字形、脸和手势、标题辨识度、纸艺融合、背景密度与遮挡余量。提示词写明比例不等于尺寸验证通过；如不符，调用图像工具修正，不以拉伸或裁切冒充独立版本。
- 默认不制作居中 4:3 裁切预览。只有用户另有要求时才附加裁切诊断图，并与两张正式成品明确区分。
- 若需要修正，锁定已批准的标题、身份和材质，针对具体缺陷最多做两次定向迭代；仍不符合时如实说明，不继续无限生成。

### 生成和交付

1. 确定本期的标题、核心动作、配色和文字布局，简短说明即可；不要为已授权的生成再问确认。
2. 使用内置 image_gen；每期分别调用工具生成 16:9 和 4:3 两张成品，保留真正的角色和风格参考输入。未知或缺失工具不能静默切换外部收费 API。
3. 分别查看 16:9 与 4:3 原图和尺寸，检查各自构图，以及同期两版内容、身份和视觉语言是否一致。修改用图像工具。
4. 保存到当前任务 `outputs/propshow-paper-covers/`；分别放入 `16x9/` 与 `4x3/`，文件名包含序号、主题和比例，例如 `01-topic-16x9.png`、`01-topic-4x3.png`，不覆盖旧版本。PNG 保留原稿，另导出便于上传的高质量 JPEG；导出不可重新生成画面。
5. 批量时提供按原视频对应的文件清单、每期两种比例的独立封面、分别按比例拼排的总览和 ZIP；JPEG 也按比例分目录。检查压缩包完整性、两种比例的配对关系及文件数量。默认 N 期应有 2N 张正式成品，说明实际新生成和沿用批准图的数量。
6. 生成封面不授权上传、改视频标题或发布。除用户明确要求外不操作平台账户。

## 可复制调用

`使用 $artifact-template-propshow-paper-covers，为这个视频分别生成 16:9 和 4:3 两张纸艺封面：<视频链接或主题>。`

`使用 $artifact-template-propshow-paper-covers，给这几期生成纸艺封面，每期分别交付 16:9 与 4:3 两张独立构图的成品，题材之间变化配色和构图。`
