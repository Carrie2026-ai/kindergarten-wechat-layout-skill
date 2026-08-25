# 幼儿园公众号排版助手

一个面向幼儿园教师、园所宣传与教研场景的微信公众号排版 Skill。

它不负责替你写完整文章，主要解决：

> **已有文稿 + 园所品牌 + 参考风格 → 一篇可读、可改、尽量兼容微信公众号的图文排版。**

## 公开版提供什么

- 分步骤排版工作流
- 品牌色与参考风格融合
- 4 个基础 Preset（不是死模板）
- 标题 / 正文 / 轻强调 / 图片的判断规则
- 微信公众号 HTML 兼容规则
- 一键复制 HTML 示例模板
- 发布前 QA 检查

## 4 个基础风格

1. **温暖自然**：家园共育、活动展示、STEM/项目活动
2. **轻童趣**：毕业季、节庆、亲子活动、需要一点儿童感但不幼稚的内容
3. **自然叙事**：课程故事、儿童观察、户外活动、过程记录
4. **清爽专业**：教研、课程成果、培训、园所专业展示

Preset 只是起点。建议最多使用 **1 个主风格 + 1 个辅助风格**。

## 推荐使用方式

1. 上传文稿；
2. 有品牌资料就一起上传；
3. 有领导喜欢的公众号截图，也可以上传；
4. 先让 Skill 分析，不急着生成最终稿；
5. 确认方向后生成排版与 HTML；
6. 打开生成页面，一键复制到公众号后台继续微调。

## 与“写作/去 AI 味”类 Skill 的关系

写作和排版是两类任务。

推荐流程：

`原始文稿 →（必要时）写作/去 AI 味 Skill → 本排版 Skill`

如果原稿已经成熟，直接排版即可。

## 目录

```text
kindergarten-wechat-layout-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── visual-principles.md
│   ├── typography.md
│   ├── style-presets.md
│   ├── wechat-html-compat.md
│   └── qa-checklist.md
└── assets/
    ├── wechat-base.html
    └── templates/
        ├── warm-natural.html
        ├── gentle-playful.html
        ├── natural-narrative.html
        └── clean-professional.html
```

## 关于模板

仓库中的模板全部使用虚构园所与占位内容，仅用于说明排版结构和兼容方法。不要把其他园所的真实文章、儿童照片、Logo、水印或专属视觉资产直接放入公共仓库。

## 许可

本项目可免费用于个人学习、教育教学及园所内部使用；未经授权不得售卖、重新打包分发、用于收费产品或商业服务。详见 [LICENSE](LICENSE)。
