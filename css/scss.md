# SASS
### get started...
1. 变量
> 定义变量以便于维护

`
$fontStack:    Helvetica, sans-serif;
$primaryColor: #333;
body {
  font-family: $fontStack;
  color: $primaryColor;
}
// css
body {
  font-family: Helvetica, sans-serif;
  color: #333;
}
`
2. 嵌套
> 选择器嵌套，层次分明

`
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  li { display: inline-block; }
  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
//css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}

nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
`
3. 导入
> 导入其它sass文件，优于css的@import

`
//_reset.scss
html,
body,
ul,
ol {
   margin: 0;
  padding: 0;
}
//base.scss
@import 'reset';
body {
  font-size: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
`
4. mixin
>让css3的编写锦上添花

`
@mixin box-sizing ($sizing) {
    -webkit-box-sizing:$sizing;     
       -moz-box-sizing:$sizing;
            box-sizing:$sizing;
}
.box-border{
    border:1px solid #ccc;
    @include box-sizing(border-box);
}
//css
.box-border {
  border: 1px solid #ccc;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
`
5. 扩展/继承
> @extend 优雅实现代码组合声明

`
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}
.success {
  @extend .message;
  border-color: green;
}
.error {
  @extend .message;
  border-color: red;
}
//css
.message, .success, .error, .warning {
  border: 1px solid #cccccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

.warning {
  border-color: yellow;
}
`
6. 四则运算
`
.container { width: 100%; }

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complimentary"] {
  float: right;
  width: 300px / 960px * 100%;
}
//css
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complimentary"] {
  float: right;
  width: 31.25%;
}
`
7. 颜色变换
`
$linkColor: #08c;
a {
    text-decoration:none;
    color:$linkColor;
    &:hover{
      color:darken($linkColor,10%);
    }
}
//css
a {
  text-decoration: none;
  color: #0088cc;
}
a:hover {
  color: #006699;
}
`
### 语法
1. 文件后缀名
    - sass:不使用{}及；
    - scss:同css，首选
2. 导入`@import`
> 导入css和css用法一样不再编译，导入scss会合并编译
3. 注释`标准注释/**/，编译到css；单行注释//不编译`
4. 变量
> $开头紧跟变量名，变量名值以：分隔，！表示默认值

`
$fontSize: 12px;
body{
    font-size:$fontSize;
}
$baseLineHeight:        2;

$baseLineHeight:        1.5 !default;
body{
    line-height: $baseLineHeight; 
}
//css
body{
    line-height:2;
}
//特殊变量：变量作为属性或在某些特殊情况下等则必须要以#{$variables}形式使用
$borderDirection:       top !default; 
$baseFontSize:          12px !default;
$baseLineHeight:        1.5 !default;

//应用于class和属性
.border-#{$borderDirection}{
  border-#{$borderDirection}:1px solid #ccc;
}
//应用于复杂的属性值
body{
    font:#{$baseFontSize}/#{$baseLineHeight};
}
`
5. 多值变量
> 多值类型分list和map类型，list类似js数组，map类似对象
`
$linkColor:         #08c #333 !default;//第一个值为默认值，第二个鼠标滑过值
a{
  color:nth($linkColor,1);

  &:hover{
    color:nth($linkColor,2);
  }
}
//css 
a{
  color:#08c;
}
a:hover{
  color:#333;
}
$headings: (h1: 2em, h2: 1.5em, h3: 1.2em);
@each $header, $size in $headings {
  #{$header} {
    font-size: $size;
  }
}
//css
h1 {
  font-size: 2em; 
}
h2 {
  font-size: 1.5em; 
}
h3 {
  font-size: 1.2em; 
}
`
6. 全局变量：！global
7. 嵌套与挑出@at-root,@at-root (without: ...)和@at-root (with: ...)
8. 混合@mixin
`
@mixin center-block {
    margin-left:auto;
    margin-right:auto;
}
.demo{
    @include center-block;
}
@mixin opacity($opacity:50) {
  opacity: $opacity / 100;
  filter: alpha(opacity=$opacity);
}
@mixin opacity($opacity:50) {
  opacity: $opacity / 100;
  filter: alpha(opacity=$opacity);
}

//css style
.opacity{
  @include opacity; //参数使用默认值
}
.opacity-80{
  @include opacity(80); //传递参数
}
//多个参数
@mixin horizontal-line($border:1px dashed #ccc, $padding:10px){
    border-bottom:$border;
    padding-top:$padding;
    padding-bottom:$padding;  
}
.imgtext-h li{
    @include horizontal-line(1px solid #ccc);
}
.imgtext-h--product li{
    @include horizontal-line($padding:15px);
}
//@content
@mixin max-screen($res){
  @media only screen and ( max-width: $res )
  {
    @content;
  }
}

@include max-screen(480px) {
  body { color: red }
}
`
9. 继承@extent
10. 占位选择器%
>如果不调用则不会有任何多余的css文件，避免了以前在一些基础的文件中预定义了很多基础的样式，然后实际应用中
不管是否使用了@extend去继承相应的样式，都会解析出来所有的样式。占位选择器以%标识定义，通过@extend调用。

`
%ir{
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
%clearfix{
  @if $lte7 {
    *zoom: 1;
  }
  &:before,
  &:after {
    content: "";
    display: table;
    font: 0/0 a;
  }
  &:after {
    clear: both;
  }
}
#header{
  h1{
    @extend %ir;
    width:300px;
  }
}
.ir{
  @extend %ir;
}
//css
#header h1,
.ir{
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
`
11. 函数
`
$baseFontSize:      10px !default;
$gray:              #ccc !defualt;        

// pixels to rems 
@function pxToRem($px) {
  @return $px / $baseFontSize * 1rem;
}

body{
  font-size:$baseFontSize;
  color:lighten($gray,10%);
}
.test{
  font-size:pxToRem(16px);
  color:darken($gray,10%);
}
`
12. 运算
$baseFontSize:          14px !default;
$baseLineHeight:        1.5 !default;
$baseGap:               $baseFontSize * $baseLineHeight !default;
$halfBaseGap:           $baseGap / 2  !default;
$samllFontSize:         $baseFontSize - 2px  !default;

//grid 
$_columns:                     12 !default;      // Total number of columns
$_column-width:                60px !default;   // Width of a single column
$_gutter:                      20px !default;     // Width of the gutter
$_gridsystem-width:            $_columns * ($_column-width + $_gutter); //grid system width`
`
13. 条件和循环
`
$lte7: true;
$type: monster;
.ib{
    display:inline-block;
    @if $lte7 {
        *display:inline;
        *zoom:1;
    }
}
p {
  @if $type == ocean {
    color: blue;
  } @else if $type == matador {
    color: red;
  } @else if $type == monster {
    color: green;
  } @else {
    color: black;
  }
}
//css
.ib{
    display:inline-block;
    *display:inline;
    *zoom:1;
}
p {
  color: green; 
}
//三目运算
if($condition, $if_true, $if_false)
//for:@for $var from <start> through <end>和@for $var from <start> to <end>
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}
//css
.item-1 {
  width: 2em; 
}
.item-2 {
  width: 4em; 
}
.item-3 {
  width: 6em; 
}
//each:@each $var in <list or map>
$animal-list: puma, sea-slug, egret, salamander;
@each $animal in $animal-list {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}
`
