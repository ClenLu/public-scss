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
import 'tezign-intelligence-common/lib/style/index.scss'
```
import from scss 
```scss
@import "~tezign-intelligence-common/lib/style/index.scss";
```
#### 局部引入
import from scss 
```scss
// 引入变量文件
@import "~tezign-intelligence-common/lib/style/variables.scss";
...
```
