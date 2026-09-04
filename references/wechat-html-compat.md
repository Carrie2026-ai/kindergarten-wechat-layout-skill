# WeChat HTML Compatibility｜微信公众号粘贴兼容规则

本文件是最终 HTML 编译规则。视觉方案完成后，必须再经过这里的约束。

## 1. 正式正文只使用这些标签
- `section`
- `span`
- `p`
- `table`
- `td`
- `strong`
- `img`

正式复制片段不要出现：
- `div`
- `class`
- `id`
- `style` 标签块
- 外部 stylesheet

预览网页外壳可以有按钮、脚本、`div / class / id`，但这些不能被复制进公众号正文。

## 2. 所有关键样式必须 inline

不要依赖选择器继承。

字号、行高、margin、padding、对齐、颜色、背景色、边框、圆角、图片宽度尽量直接写在当前元素或直接父级。

## 3. 颜色

只使用六位十六进制：

`#RRGGBB`

禁止：
- `rgba()`；
- 透明色；
- 渐变。

## 4. 背景

稳定优先使用：

`background-color:#RRGGBB;`

禁止：
- `background-image`；
- `linear-gradient()`；
- `radial-gradient()`；
- CSS 格子纹；
- CSS 纸张纹理；
- 外链背景图。

## 5. 双层 section

微信公众号可能剥掉粘贴内容最外层容器的背景色。

因此整篇背景统一采用：

```html
<section style="margin:0;padding:0;background-color:#FFFFFF;">
  <section style="margin:0;padding:0;background-color:#F6F1E8;">
    ...正式正文...
  </section>
</section>
```

最外层是牺牲层；第二层才是真正的主背景。

## 6. 连续背景

如果希望产生“整篇米黄 / 奶油底”的感觉，不依赖一个大容器。

内部每一个主要区块继续铺同一背景色：

```html
<section style="margin:0;padding:24px 18px;background-color:#F6F1E8;">...</section>
<section style="margin:0;padding:18px;background-color:#F6F1E8;">...</section>
<section style="margin:0;padding:24px 18px;background-color:#F6F1E8;">...</section>
```

这样即使某一层样式被平台处理，整篇仍更容易保持连续色块。

## 7. 布局

禁止依赖：
- `position:absolute`；
- `position:relative`；
- `position:fixed`；
- flex；
- grid；
- transform；
- 复杂 box-shadow。

需要双栏时，只使用简单 `table / td`。

## 8. 圆角与边框

可少量使用：
- `border-radius`；
- `border`；
- `border-top`；
- `border-left`；
- `border-bottom`；
- dashed / solid。

边框用于建立层级，不做装饰堆叠。

## 9. 图片

真实图片使用 `<img>`。

优先信任已经进入公众号图库的 `mmbiz.qpic.cn` 地址。

没有真实可用地址时：
- 不生成空 `src`；
- 不生成伪造 URL；
- 用一个可删除的浅色 section 作为占位；
- 在最终交付中注明“放什么图 / 从哪来 / 没有图怎么降级”。

## 10. 复杂氛围必须图片化

以下都不要用 CSS 画：
- 格子纸；
- 水彩纸；
- 叶子；
- 小花；
- 星星；
- 小精灵；
- 书本角色；
- 手绘边角；
- 装饰纹理。

它们应该来自：
1. 园所自有手绘 / IP；
2. 已获得授权的秀米 / 135 素材；
3. 用户自行制作或合法生成的 PNG / JPG；
4. 最终上传至公众号图库或通过兼容流程进入公众号。

## 11. 一键复制

ClipboardItem 只写 `text/html`：

```javascript
var item = new ClipboardItem({
  'text/html': new Blob([html], {type:'text/html'})
});
```

不要同时写 `text/plain`。

按钮、提示、调试 UI 必须在复制区之外。

## 12. 最终兼容心法

不要问：

> “浏览器里还能不能做得更漂亮？”

要问：

> “粘贴以后还活着什么？”

只设计那些粘贴后大概率还能保留的结构；复杂氛围交给真实素材图片。
