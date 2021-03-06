# web events(值均为script)

### PC端

1. window事件属性（适用于body标签）

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onafterprint  | 在打印文档之后运行脚本|New|
| onbeforeprint    | 在文档打印之前运行脚本  |New|
| onbeforeonload | 	在文档加载之前运行脚本 |New|
| onblur | 	当窗口失去焦点时运行脚本 | |
| onerror | 当错误发生时运行脚本 |New|
| onfocus | 当窗口获得焦点时运行脚本 ||
| onhaschange | 当文档改变时运行脚本 |New|
| onload | 当文档加载时运行脚本 ||
| onmessage | 当触发消息时运行脚本 |New|
| onoffline | 当文档离线时运行脚本 |New|
| ononline | 当文档上线时运行脚本 |New|
| onpagehide | 当窗口隐藏时运行脚本 |New|
| onpageshow | 	当窗口可见时运行脚本 |New|
| onpopstate | 当文档执行再执行操作（redo）时运行脚本 |New|
| onresize| 当调整窗口大小时运行脚本 |New|
| onstorage| 当文档加载加载时运行脚本 |New|
| onundo| 当 Web Storage 区域更新时（存储空间中的数据发生变化时） |New|
| onunload| 当用户离开文档时运行脚本 |New|

2. form事件属性(适用于所有h5元素，常用于表单)
| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onblur  | 当元素失去焦点时运行脚本||
| onchange  | 当元素改变时运行脚本||
| oncontextmenu  | 当触发上下文菜单时运行脚本|New|
| onfocus  | 当元素获得焦点时运行脚本|New|
| onformchange  | 当表单改变时运行脚本|New|
| onforminput  | 当表单获得用户输入时运行脚本|New|
| oninput  | 当元素获得用户输入时运行脚本|New|
| oninvalid  | 当元素无效时运行脚本|New|
| onreset  | 当表单重置时运行脚本。HTML 5 不支持||
| onselect  | 当选取元素时运行脚本||
| onsubmit  | 当提交表单时运行脚本||

3. keyboard事件(适用于所有h5元素)
| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onkeydown  | 当按下按键时运行脚本||
| onkeypress  | 当按下并松开按键时运行脚本||
| onkeyup  | 当松开按键时运行脚本||
4. mouse事件(适用于所有h5元素)

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onclick  | 当单击鼠标时运行脚本||
| ondblclick  | 当双击鼠标时运行脚本||
| ondrag  | 当拖动元素时运行脚本|New|
| ondragend  | 当拖动操作结束时运行脚本|New|
| ondragenter  | 当元素被拖动至有效的拖放目标时运行脚本|New|
| ondragleave  | 当元素离开有效拖放目标时运行脚本|New|
| ondragover  | 当元素被拖动至有效拖放目标上方时运行脚本|New|
| ondragstart  | 当拖动操作开始时运行脚本|New|
| ondrop  | 当被拖动元素正在被拖放时运行脚本|New|
| onmousedown  | 当按下鼠标按钮时运行脚本||
| onmousemove  | 当鼠标指针移动时运行脚本||
| onmouseout  | 当鼠标指针移出元素时运行脚本||
| onmouseover  | 当鼠标指针移至元素之上时运行脚本||
| onmouseup  | 当松开鼠标按钮时运行脚本||
| onmousewheel  | 当转动鼠标滚轮时运行脚本|New|
| onscroll  | 当滚动元素滚动元素的滚动条时运行脚本|New|

5. media事件(适用于所有h5元素,常用于媒体元素)

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onabort  | 当发生中止事件时运行脚本||
| oncanplay  | 当媒介能够开始播放但可能因缓冲而需要停止时运行脚本|New|
| oncanplaythrough  | 当媒介能够无需因缓冲而停止即可播放至结尾时运行脚本|New|
| ondurationchange  | 当媒介长度改变时运行脚本|New|
| onemptied  | 当媒介资源元素突然为空时（网络错误、加载错误等）运行脚本|New|
| onended  | 当媒介已抵达结尾时运行脚本|New|
| onerror  | 当在元素加载期间发生错误时运行脚本|New|
| onloadeddata  | 当加载媒介数据时运行脚本|New|
| onloadedmetadata  | 当媒介元素的持续时间以及其他媒介数据已加载时运行脚本|New|
| onloadstart  | 当浏览器开始加载媒介数据时运行脚本|New|
| onpause  | 当媒介数据暂停时运行脚本|New|
| onplay  | 当媒介数据将要开始播放时运行脚本|New|
| onplaying  | 当媒介数据已开始播放时运行脚本|New|
| onprogress  | 当浏览器正在取媒介数据时运行脚本|New|
| onratechange  | 当媒介数据的播放速率改变时运行脚本|New|
| onreadystatechange  | 当就绪状态（ready-state）改变时运行脚本|New|
| onseeked  | 当媒介元素的定位属性 [1] 不再为真且定位已结束时运行脚本|New|
| onseeking  | 当媒介元素的定位属性为真且定位已开始时运行脚本|New|
| onstalled  | 当取回媒介数据过程中（延迟）存在错误时运行脚本|New|
| onsuspend  | 当浏览器已在取媒介数据但在取回整个媒介文件之前停止时运行脚本|New|
| ontimeupdate  | 当媒介改变其播放位置时运行脚本|New|
| onvolumechange  | 当媒介改变音量亦或当音量被设置为静音时运行脚本|New|
| onwaiting  | 当媒介已停止播放但打算继续播放时运行脚本|New|

6. 其它事件

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| onshow  | 当 <menu> 元素在上下文显示时触发||
| ontoggle  | 当用户打开或关闭 <details> 元素时触发||

### 移动端

>  理解click的300ms的延迟响应
   Click事件在移动手机开发中有300ms的延迟，因为在手机早期，浏览器系统有放大和缩放功能，用户在屏幕上点击两次之后，
   系统会触发放大或者缩放功能，因此系统做了一个处理，当触摸一次后，在300ms这段时间内有没有触摸第二次，
   如果触摸了第二次的话，说明是触发放大或缩放功能，否则的话是click事件。因此当click时候，所有用户必须等待于300ms后才
   会触发click事件。所以当在移动端使用click事件的时候，会感觉到有300ms的迟钝。

1. touch事件

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
| touchstart  | 当手指放在屏幕上触发||
| touchmove  | 当手指在屏幕上滑动时，连续地触发||
| touchend  | 当手指从屏幕上离开时触发||
| touchcancel  | 当系统停止跟踪时触发; 该事件暂时使用不到||
| touches  | 表示当前跟踪的触摸操作的touch对象的数组||
| targetTouches  |  特定于事件目标的touch对象的数组||
| changedTouches | 上次触摸以来发生了什么改变的touch对象的数组||

2. gesture事件

| Properties    | Description | Mark|
| :------------ |:--------------:|-----:|
|  gesturestart  | 当一个手指已经按在屏幕上，而另一个手指又触摸在屏幕时触发||
|  gesturechange  | 当触摸屏幕的任何一个手指的位置发生改变的时候触发||
| gestureend | 当任何一个手指从屏幕上面移开时触发||

> 触摸事件和手势事件的之间关系：
当一个手指放在屏幕上时，会触发touchstart事件，而另一个手指触摸在屏幕上时
触发gesturestart事件，随后触发基于该手指的touchstart事件。
如果一个或两个手指在屏幕上滑动时，将会触发gesturechange事件，但是只要有一个手指移开时候，则会触发gestureend事件，
紧接着会触发touchend事件。
手势的专有属性:
rotation: 表示手指变化引起的旋转角度，负值表示逆时针，正值表示顺时针，从0开始；
scale: 表示2个手指之间的距离情况，向内收缩会缩短距离，这个值从1开始的，并随距离拉大而增长。
