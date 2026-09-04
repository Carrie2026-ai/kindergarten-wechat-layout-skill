# Changelog

## V0.3 — 2026-09-04

### 双轴排版体系
- 将原 4 个 Preset 明确调整为 Content Preset，只负责内容结构与阅读节奏。
- 新增 6 个 Visual Archetype，负责视觉方向与装饰密度。
- 新工作模型：`Content Preset × Visual Archetype × Brand Profile × Reference Style × WeChat Compiler`。

### 领导 / 园所偏好
- 新增 `references/leadership-preference-card.md`。
- 支持从 2–5 张参考截图中提取园所 / 领导视觉偏好卡。
- 偏好卡记录标题、颜色、图片、装饰、背景、信息密度、卡片密度、品牌露出与避免项。

### 视觉原型
- 新增 `references/visual-archetypes.md`。
- 新增 6 个微信安全视觉骨架：园所官方型、秀米轻童趣型、温暖活动型、课程故事杂志型、成果展示型、极简园刊型。
- 明确这些原型是原创抽象规则，不复制第三方完整秀米 / 135 模板。

### 秀米协作
- 秀米微调建议改为与 Visual Archetype 联动。
- 不同原型对应不同的最后 10% 微调重点。

### QA
- 新增 Content Preset / Visual Archetype 双轴检查。
- 新增领导偏好卡一致性检查。
- 新增第三方模板版权边界检查。

## V0.2 — 2026-09-04

### 微信兼容
- 明确正式正文仅使用 `section / span / p / table / td / strong / img`。
- 强制 inline style。
- 颜色统一使用 `#RRGGBB`。
- 禁止 `rgba()`、渐变、`background-image`、CSS 底纹。
- 禁止使用 absolute / relative / fixed 作为正式正文布局依赖。
- 不使用 flex / grid 做关键布局。
- 增加“双层 section”背景保留策略。
- 增加“相邻 section 连续铺同色背景”的整篇氛围策略。
- 一键复制 ClipboardItem 改为只写 `text/html`。

### 图片与装饰
- 树叶、小花、小精灵、格纹、纸张纹理等复杂装饰统一改为真实图片素材。
- 没有真实图片 URL 时不生成空 `src` 或伪地址，改为可删除占位区。
- 新增图片位置清单规则。

### 人工微调
- 新增 `references/xiumi-tuning-guide.md`。
- 最终输出强制包含 3–6 个秀米微调位置。
- 增加“不建议再动”的保护规则，避免用户在秀米中二次过度设计。

### 模板
- 四个公开 Preset 重新编译为更保守的微信正文片段。
- 新增公开版 `wechat-base.html` 一键复制底座。
