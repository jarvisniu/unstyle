# unstyle

> Write less styles

## 已加入
【布局】
显示(display): block, inline, inline-block
显隐: invisible (visibility: hidden), visible (visibility: visible)
定位(position): absolute, relative, fixed, sticky
浮动: float-left | right, clearfix

【盒模型】
边距: margin(m-x-1), padding(p-x-1), x@a(all四周), tblr(上下左右), hv(水平垂直), m-a
尺寸: width(w-), height(h-), minus height(h-m-), max-, min-, w-<m>-<n>
全尺寸(可以去掉一个吗？): full-height, full-width, w-full, h-full
边框: 样式 b-<none solid dotted dashed double hidden>, 圆角 b-r-6, 圆形角 b-round, 更细(半像素) b-thin
上下左右: top, bottom, left, right

【文本】
字号(TODO): font-size(f-s-1_5) = font-size: 1.5em;
行高: line-height(l-h-)
对齐: text-align: left, right, center, justify
样式: bold, italic, underline, line-through, text-ellipsis(...), break-word(word-break: break-all)
对齐: vertical-align: top ———— 用 v-a-top(推荐，因为不是盒模型) 还是 vertical-align-top(不推荐，太长)
空白: nowrap, pre, pre-line, pre-wrap

【杂项】
颜色: 文字 color-<color>, 背景 bg-<color>, 边框 b-<color>, 灰阶 <x>-gray-[1-e]
禁止: 换行 no-wrap (white-space: nowrap), 粗体 no-bold (font-weight: normal), 选择 no-select (user-select: none), 拖拽 no-drap (user-drag: none)

## 需增补

pull-left, right
b-x-thin 需要吗?因为有b-thin可以组合就不用。 

## 考虑中
justify-content -> j-, align-items -> a-
outline: ol- | o-(可能与overflow混淆，但值不混淆，可以共用)，它也算盒模型
	overflow: hidden scroll auto overlay? visible
	outline: style, color, width, offset!
垂直居中: align-center = [-webkit-]align-items: center;
语义化边距尺寸: sm=5, md=10, lg=20, xl=40

## 冲突 Conflicts

[x] m-h-10:  margin-horizontal vs. min-height. 解决方法: min-height 用 min-h-10;

## 设计决策 Design decisions

长度取值：取哪些？
	原则: 递增1/3、1/4、1/5从左到右三选一
	不好: 10-12-16-20-24-32-40-48-64-72-100
	好: 10-12-15-20-25-30-40-50-60-80-100
	宽高好: 100-120-150-200-250-300-400-500-600-800-1000
连字符: 要还是不要？
	例如: margin-top-10: 用 m-t-10 还是 mt10？
	例如: font-size-15: 用 f-s-15 还是 fs-15？用f-s
	例如: overflow -> of | o?
	答: 要，可以增强可读性，且能避免冲突
	原则: 原来有-的一定继续保留
