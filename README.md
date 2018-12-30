# unstyle

> Write less styles

## 安装

```
npm install @jarvisniu/unstyle
```
或
```
yarn add @jarvisniu/unstyle
```

## 同类项目

- [Tailwind CSS](https://github.com/tailwindcss/tailwindcss)
- [Primer Utilities](https://styleguide.github.com/primer/utilities/)
- [Bootstrap Utilities](https://getbootstrap.com/docs/4.1/utilities/borders/)

## 设计决策

- 要连字符：比如 p-l-5 不能 pl5，可读性差，且很容易冲突。
- 不加字号：自己定义分级的，比如 1 ~ 6，可以参考 `font-size.css` 。不要用 px, rem 的，又多又杂不统一。
- 不加弹性框：用的少，方案还没想好，而且有专门的解决方案 [flex.css](https://github.com/lzxb/flex.css)。
- 不引用源码定制：使用CSS变量达到既可以不引用源码，又可以定制样式的目的。目前仅支持配置边框颜色。

## 下个版本

- 无

## 考虑中

- outline: ol- | o- (可能与 overflow 混淆，但值不混淆，可以共用)，它也算盒模型。
  - overflow: hidden scroll auto overlay? visible
  -	outline: { style }, { color }, { width }, { offset }!
  -	opacity: 0-10
- 垂直居中: align-center = [-webkit-]align-items: center;
- 语义化边距尺寸: sm=5, md=10, lg=20, xl=40 或 s=5, m=10, l=20

## 文档
布局
- 显示(display): block, inline, inline-block
- 定位(position): absolute, relative, fixed, sticky
- 浮动: float-left | right, clearfix
- 全尺寸: full-size, full-height, full-width, w-full, h-full
- 溢出: overflow(o-): visible scroll hidden auto

盒模型
- 边距: margin(m-x-1), padding(p-x-1), x@a(all四周), tblr(上下左右), xy(轴的方向), m-x-a
- 尺寸: width(w-), height(h-), minus height(h-m-), max-, min-, w-{ m }-{ n }
- 全尺寸: full-size, full-height, full-width, w-full, h-full
- 边框
  - 样式 b-{ none solid dotted dashed double hidden }
  - 圆角 b-r-{ length }
  - 圆形 b-circle
  - 粗细 b-thin(半像素), b-thick(2px)
- 上下左右: top, bottom, left, right

文本
- 行高: line-height(l-h-)
- 对齐: text-align: left, right, center, justify
- 样式: bold, italic, underline, line-through, text-ellipsis(...), break-word(word-break: break-all)
- 对齐: vertical-align: top = v-a-top
- 空白: nowrap, pre, pre-line, pre-wrap

杂项
- 颜色: 文字 color-{ color }, 背景 bg-{ color }, 边框 b-{ color }, 灰阶 { x }-gray-[1-e]
- 禁止: 换行 no-wrap (white-space: nowrap), 粗体 no-bold (font-weight: normal), 选择 no-select (user-select: none), 拖拽 no-drag (user-drag: none)
- 光标: cursor(c-{ style }): default none pointer crosshair text move
- 显隐: invisible (visibility: hidden), visible (visibility: visible)

## FAQ

### 如何改变边框颜色？
覆盖下面的内部CSS变量即可。
> 注意：加在 `:root` 或 `html` 上可能会由于导入顺序的原因而导致无法覆盖。
``` css
body {
  --unstyle-border-color: pink;
}
```
