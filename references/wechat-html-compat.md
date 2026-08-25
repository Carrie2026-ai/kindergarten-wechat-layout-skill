# 微信公众号 HTML 兼容规则

## 原则
微信公众号兼容稳定性优先于网页炫技。

## 正文区域优先使用
- `section`
- `p`
- `span`
- `strong` / `b`
- `img`
- 简单 `table`（双图/三图并排时可用）

关键样式尽量直接写为 inline CSS。

## 尽量避免
- 依赖外部 CSS
- 关键样式依赖 class
- flex / grid 复杂布局
- absolute / fixed 定位
- transform 承担关键对齐
- JavaScript 才能呈现正文
- 复杂动画、滤镜和浏览器专属特性

## 核心属性
字号、行高、颜色、对齐、margin、padding、图片宽度等关键属性，尽量写在当前元素或直接父元素上，减少多级继承。

## 图片
- 单图：`display:block;width:100%;height:auto;`
- 需要圆角时使用轻圆角，避免复杂阴影。
- 双图/三图并排：优先简单 `table`，每格显式写宽度与 vertical-align。
- 不强行裁掉关键人物和活动信息。

## 居中
重要居中优先使用 `text-align:center` 等直接规则，不依赖 flex/transform。

## 一键复制
页面操作 UI 放在 `#wx-preview` 之外；复制时只复制正文区。
优先同时写入：
- `text/html`
- `text/plain`

如 Clipboard API 不可用，可回退到选区 + `execCommand('copy')`。

## 模板策略
优先复制 `assets/templates/` 中已有的稳定种子模板再调整，不要每次从零生成复杂 HTML。
