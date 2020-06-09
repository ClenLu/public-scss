### 文档

### 文档说明
```
├── commons（公用class）
│   ├── attributes.scss 常用的属性class 
│   ├── colors.scss 颜色相关的class
│   ├── layouts.scss 布局排版相关的class
│   ├── operations.scss 交互相关的class
│   └── texts.scss 字体文本相关的class(字体大小，文本间隔...)
├── builds.scss build 工具方法，用来生成公用class
├── index.scss 入口文件，项目中引用这个文件可以导入所有基础样式和公用class
├── mixins.scss mixin 方法，包含了常用的 css 模板
├── reset.scss 用来重置 html 的默认样式
├── variables.json variables.scss的json版本，通过 scripts/scssToJson.js 生成
└── variables.scss 这里定义所有 scss 变量
```

### 使用说明
#### 引入所有的基础样式和公用class
import from js 
```js
import 'public-scss/index.scss'
```
import from scss 
```scss
@import "~public-scss//index.scss";
```
#### 局部引入
import from scss 
```scss
// 引入变量文件
@import "~public-scss//variables.scss";
...
```
### 公用 class

#### attributes.scss
包含属性类的公共 class

```css
// 圆角
.border-radius {
  border-radius: $border-radius;
}
.border-radius-small
.border-radius-large
// 阴影
.box-shadow-1 {
  box-shadow: $box-shadow-1;
}
.box-shadow-2
.box-shadow-3
.box-shadow-4
// 透明度
.opacity-40 {
  opacity: 0.4;
}
.opacity-50
.opacity-60
.opacity-70
.opacity-80
.opacity-100
// 边框
.border-left {
  border-left: 1px solid $color-border;
}
.border-right
.border-top
.border-bottom
.border-all {
  border: 1px solid $color-border;
}
```

#### colors.scss
包含颜色的相关公共 class

```css
.color-primary {
  color: $color-primary
}
.bgc-primary {
  background-color: $color-primary
}
.bdc-primary {
  border-color: $color-primary
}
// name 值可选 warning hint help text text-light text-dark bg-dark
.color-[name]
.bgc-[name]
.bdc-[name]
```

#### layouts.scss 
布局排版相关的class

```css
// 间距 gap 可选值 0、 4,5 的倍数（从 1 到 40）
.mt-[gap] { margin-top : [gap]px }
.pt-[gap] { padding-top : [gap]px }
.mb-[gap] { margin-bottom : [gap]px }
.pb-[gap] { padding-bottom : [gap]px }
.ml-[gap] { margin-left : [gap]px }
.pl-[gap] { padding-left : [gap]px }
.mr-[gap] { margin-right : [gap]px }
.pr-[gap] { padding-right : [gap]px }
.margin-[gap] { margin : [gap]px }
.padding-[gap] { padding : [gap]px }

.margin-auto { margin: auto; }
.ml-auto { margin-left: auto; }
.mr-auto { margin-right: auto; }
// 栅格布局类，12 列
// num 可选值 1 - 12
.cols .col-[num]
// gap 列之间的间隔，可选值 10 20 40 80 120
.cols.gutter-[gap]

// display 相关
.display-none { display: none; }
.display-block { display: block; }
.display-inline-block { display: inline-block; }
// flex 布局系列
.display-inline-flex { display: inline-flex; }
.display-flex { display: flex; }
.display-flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
.flex-align-items-start { align-items: flex-start; }
.flex-align-items-center { align-items: center; }
.flex-align-items-end { align-items: flex-end; }
.flex-justify-content-start { justify-content: flex-start; }
.flex-justify-content-space-between { justify-content: space-between; }
.flex-justify-content-space-around { justify-content: space-around; }
.flex-justify-content-center { justify-content: center; }
.flex-justify-content-end { justify-content: flex-end; }
.flex-1 { flex: 1; }
.flex-2 { flex: 2; }
// position 系列
.position-relative { position: relative; }
.position-absolute
.position-fixed

.position-absolute-bottom {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
}
.position-fixed-bottom {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
}
// 浮动相关
.clear-fix // 清除浮动
.float-left { float: left; }
.float-right { float: right; }
// 大小设置
.full-width { width: 100%; }
.full-size {
  width: 100%;
  height: 100%;
}
.width-0 { width: 0; }
// 滚动设置
.overflow-hidden { overflow: hidden; }
// 滚动条 系列
.scroll-y { overflow-y: scroll; }
.scroll-y-auto { overflow-y: auto; }
.scroll-view {
  display: block;
  width: 100%;
  height: 100%;
  overflow-y: auto;
}
```

#### texts.scss 
字体文本相关的class(字体大小，文本间隔...)
```css
h1, h2, h3, h4, h5, h6, .h1, .h2, .h3 { color: $color-text-dark }
h1, .h1 { font-size: 24px; }
h2, .h2 { font-size: 20px; }
h3, .h3 { font-size: 16px; }
// 字体大小 size 可选值 12 - 60 之间
.fz-[size] { font-size: [size]px; }
// font-weight
.fw-light { font-weight: $font-weight-light; }
.fw-normal { font-weight: $font-weight-normal; }
.fw-bold { font-weight: $font-weight-bold; }
// 行高
.lnr { line-height: inherit; }
.lh-none { line-height: 1; }
.lh-normal { line-height: $line-height; }
.lh-small { line-height: $line-height-small; }
.lh-large { line-height: $line-height-large; }
// 字间距 num 可选值 0 到 8
.lsp-[num] { letter-spacing: [num]px; }
// 文字排列
.text-left { text-align: left !important; }
.text-center { text-align: center !important; }
.text-right { text-align: right !important; }
.text-justify { text-align: justify; }
// 单行文本自动省略
.text-ellipsis 
// 文本换行
.word-break-all { word-break: break-all; }
// 不换行
.text-nowrap { white-space: nowrap; }
```