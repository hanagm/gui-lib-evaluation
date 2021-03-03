# GUI 引擎评价指标

github 上的开源 GUI 引擎至少有数十个，如何去评估它们的优劣，如何选择你需要的 GUI 引擎？这个是艰巨的任务，每个人的需求不一样，GUI 开发者的意图也不同，很难找到统一的标准去选出最好的 GUI。QT 是最强大的，没有之一，但也不一定适合你。在 [这篇文章](https://www.zhihu.com/question/283787183/answer/433510666) 有句话：“商业引擎看起来功能很齐全，但是实际使用起来你就知道有多少坑。” 这句话挺有意思，它即适合游戏引擎，也适合 GUI 引擎。demo 看起来很好，技术看起来很先进，用起来才知道有多少坑！所以事先做一个完整的评估是很有必要的。

虽然客观的评价一个 GUI 引擎很难，但不管怎么样，总有些指标可以提供有价值的参考，尽管这些指标在遇到不同使用的场景，不同的公司背景，不同的个人喜好，它们所占的权重也大不相同。但是并不能抹杀这些指标的价值，关键在于如何根据自己的需要调整它们的比重。

在 [《这个开源的 6 千行 UI 框架，能打败 QT，MFC 吗？》](https://www.zhihu.com/question/66934513/answer/248036488) 这篇文章里，[诸葛不亮](https://www.zhihu.com/people/ZgblKylin) 的 37 问给了我极大的启发，在开发 AWTK 的过程中，多次重读这篇文章，这篇文章堪称是 GUI 引擎开发者的指路明灯。

> 如果诸葛大侠不介意，为了活跃气氛，我就把本文提到的指标称为《诸葛不亮-李先静 GUI 引擎评价指标》，把诸葛大侠放在前面，是表示对他的感谢，把我的名字放在里面，是由我承担一些人的指责。

先开个头，算是抛砖引玉吧。后续会不断完善，希望大家也把自己选择 GUI 引擎时的指标补充进来。

## 1. 基本指标

#### 1.1 开发者的心态

> 当你用他们的 GUI 时，他们是感谢你的支持，还在觉得你欠他们的呢？如果他们没有心存感谢，你最好别用。否则，遇到问题时，你怎么能指望他们帮你解决呢？

#### 1.2 帮助文档

> 是否有《API 手册》、《使用手册》、《常见问题》、《移植文档》和《HowTo》，文档是否在定期更新？

#### 1.3 示例代码

> 是否有简单的入门示例、各种控件的的用法、完整功能的示例？

#### 1.4 代码风格

> 目录名、文件名、类名、函数名、函数参数、局部变量名、全局变量名、注释和缩进是否一致。

#### 1.5 编程语言

>目前支持哪些开发语言？支持新的开发语言是否容易？编程风格是否与对应的语言相符？不同语言绑定的代码能否同步更新（否则很容易落后于核心引擎）？
>
> 对于 GUI 引擎来说，支持多种编程语言是重要的，可以满足不同的开发者的需要。对于使用者来说，GUI 是否提供了你需要的编程语言才是最重要的。
 

#### 1.6 支持的平台

> 对于 GUI 引擎来说，支持多种平台是重要的，可以满足不同的开发者的需要。对于使用者来说，支持多种平台也是重要的，你现在开发嵌入式系统，过段时间你可能要开发一个 APP 控制你设备，没有必要浪费时间去学习不同的 GUI。
>
> GUI 是否支持目标平台的界面风格，是否提供跨平台的运行库，是否对平台基本的原生功能进行了包装，能否扩展新的功能。是否支持平台原生输入法？ 

#### 1.7 可视化的界面设计工具

> 所见即所得方式开发界面可以降低学习门槛，提高开发效率。

#### 1.8 可视化的界面设计工具是否是用该 GUI 本身开发的

> 用该 GUI 本身开发的界面设计工具，可以验证该 GUI 本身的功能是否强大和稳定。
> 
> 另外用该 GUI 本身开发的界面设计工具，才能把界面设计工具做得易用。比如 TabControl 控件，在设计时可以切换页面，只有用该 GUI 本身开发的界面设计工具才容易实现。

#### 1.9 在开发环境模拟运行

> 运行环境和开发环境往往不同， 如果每次都要部署一下才能看到效果，那开发速度一定上不来。

#### 1.10 用 XML/JSON 等数据来描述界面

> XML/JSON 是声明式的语法，不但手工编写比写程序容易，也方便借助工具的支持。
>
> 对于嵌入低端嵌入式系统来说，XML/JSON 效率不高，最好的办法是运行时转换成高效的二进制格式。就像代码一样，编译之前的代码给人看，编译之后的代码给机器看。

#### 1.11 用 XML/CSS 等数据来描述界面的风格

> XML/JSON 是声明式的语法，不但手工编写比写程序容易，也方便借助工具的支持。
> 
> 把界面风格从 UI 描述文件和代码中剥离出来，也有利于后期的维护，毕竟界面效果是最容易变化的。
>
> 对于嵌入低端嵌入式系统来说，XML/JSON 效率不高，最好的办法是运行时转换成高效的二进制格式。就像代码一样，编译之前的代码给人看，编译之后的代码给机器看。

#### 1.12 字体格式

> 支持点阵字体吗？支持矢量字体吗？支持自定义字体格式吗？支持只加载部分字体到内存吗？配套工具完善吗？

#### 1.13 图片格式

> 支持常见的 png/jpg/gif/bmp 格式吗？支持 SVG 等矢量图形吗？能扩展支持新的格式吗？

#### 1.14 输入法

> 支持拼音输入法吗？支持软键盘的 T9 输入法吗？支持硬键盘的 T9 输入法吗？支持语音输入法吗？支持手写输入法吗？可以扩展支持新的输入吗？是否支持平台原生输入法？

#### 1.15 基本架构模式

> 是否内置提供支持 MVC、MVP 和 MVVM 等架构模式？是否支持 Vue、React 和小程序类似的开发方式？

## 2. 功能指标

#### 2.1 高清屏

> 是否支持高清屏？在 PC 上运行时界面变糊了，在手机上运行时字体变小了，都是不支持高清屏的特征。不支持高清屏就不用谈什么跨平台了。

#### 2.2 矢量图 API

> 矢量图 API 是非常重要的，强大矢量图 API 能实现很多神奇的效果。个人觉得 HTML5 Canvas 2D API 是最好的矢量图 API。用 cairo、skia、agge 和 nanovg 这些开源的库很容易实现类似的 API。
> 
> GUI 一定要提供一个抽象的接口，在不同的情况下，可以无缝的切换到最优的实现方案上。比如在嵌入式平台用 agge，在嵌入式 linux 平台用 cairo，在 PC 上用 skia 或 nanovg。

#### 2.3 窗口动画

> 是否支持窗口动画？窗口动画的种类是否够用？是否可以扩展自己的窗口动画。窗口动画的效率如何？窗口动画使用是否方便？

#### 2.4 控件动画

> 是否支持控件动画？支持那些控件动画？是否支持自定义的控件动画？控件动画使用是否方便？控件动画的参数有哪些？是否可以停止、暂停和播放控件动画。

#### 2.5 内置控件是否丰富

> 是否有日历选择控件？是否有文件选择控件？是否有颜色选择控件？是否有 RichText 控件？是否有你目前需要的控件和将来可能用到的控件？

#### 2.6 控件组合是否方便

> 有的 GUI 把控件分成叶子节点控件和容器控件，label、image、edit 和 button 都是叶子节点控件。这样做灵活性很差，往 button 放个图片或者动画，往 label 里放个图片，往 edit 里放一个"清除"/"查找"的 button，不是方便的事吗，为什么要限制呢？

#### 2.7 自定义控件

> 没有一个 GUI 能够满足所有的需求，如果不支持自定义控件就悲催了。这样一个简单的需要，在有的 GUI 里却需要修改 GUI 引擎的代码，那就不好玩了。

#### 2.8 布局 (layout) 参数

> 通过布局参数控制控件布局，可以让应用程序适用于不同大小的屏幕。是否支持布局参数，布局功能是否强大，是否可以扩展自定义布局？

#### 2.9 控件自定义属性

> 如果控件支持自定义属性，用户可以存放自己的数据到控件中，可以避免使用全局变量，是个极为方便的特性。

> 如果控件支持自定义属性，对 GUI 进行扩展也很方便，比如 AWTK-MVVM 的绑定规则就使用了用户自定义属性，如果将 AWTK-MVVM 移植到 Qt 就很容易，因为 Qt 也支持自定义属性，要移植到 emwin 就麻烦不少。

#### 2.10 控件：label

> label 是最简单的控件，要做好也不容易。就像炒饭是厨师的基本功一下，label 就是 GUI 开发者的基本功。 支持 style（字体、颜色和对齐等各种参数）吗？支持 unicode 的换行规则吗？支持滚动显示吗？支持省略号显示吗？支持 bidi 算法吗？支持动画（比如打字效果和拨号中那种）。滚动显示支持得到焦点时才滚动吗？支持垂直方向排版吗？

> 当然把 label 和 scroll_label 分成两个控件好点，实现简单而且在低端平台无需支持一下不必要的特性。总之，用户需要时就要有这些功能。

#### 2.11 控件：image

> 支持旋转和缩放吗？ 支持旋转和缩放动画吗？支持居中、平铺、x 平铺、y 平铺、九宫格、三宫格、缩放和按比例缩放等各种绘制效果吗？支持显示文本吗？支持点击吗？支持勾选吗？

#### 2.12 控件：edit

> 支持 edit 不难，要做好却不容易：支持拷贝、剪切和粘贴吗？支持撤销和重做吗？支持通过键盘和鼠标选择吗？支持输入法吗？可以根据各种输入类型自动选择软键盘吗？可以自定义软键盘吗？可以指定获得焦点时软件盘是否自动开启吗？可以指定获失去焦点时软件盘是否自动关闭吗？支持设置有效性检查函数吗？支持失去焦点时自动修复输入值吗？支持失去焦点时提示输入有误吗？支持输入提示吗？支持输入有变化时提示吗？支持时间、日期和 IP 地址等格式输入吗？

#### 2.13 控件：button

> 是否支持长按？是否支持设置长按时间？是否支持重复触发？是否支持图标？是否支持子控件（如图片和动画）？

#### 2.14 控件：软键盘

> 软键盘使用 XML/JSON 描述吗？可以定制软键盘（键盘布局和风格）吗？定制软键盘需要修改代码吗？软键盘可以用纯方向键切换焦点吗？

#### 2.15 控件：table view

> 支持放入进度条、选择框、按钮、图片和编辑器吗？支持 View 和 Model 分离吗？能支持千万级别的数据吗？

#### 2.16 控件：code editor

> 有些高手常用两个指标来衡量 GUI 的功能：1. 能用它开发一个记事本吗？ 2. 能用它开发一个界面设计器吗？如果支持 code editor，就可以用它实现一个功能更强大的记事本。

#### 2.17 style

> 是否支持设置圆角半径？是否支持对部分角设置圆角？是否可以分别设置上下左右的边框？是否支持自定义的状态？

#### 2.18 对话框高亮

> 弹出对话框时：是否支持对话框背景变暗？是否支持对话框背景动态变暗？是否支持对话框背景动态变模糊？是否支持新的对话框高亮策略。

#### 2.19 键盘切换焦点

> 是否支持键盘切换焦点？是否支持上下左右切换焦点（有的设备只有方向键和确认键）？是否支持设置切换焦点的键值？

#### 2.20 截屏

> 是否支持截屏？

#### 2.21 操作反馈

> 是否支持按键音？不同的控件支付支持不同的按键音？是否支持触屏震动？

#### 2.22 Accessibility

> 是否支持字体整体放大？是否支持读屏软件？

#### 2.23 存储接口

> 有没有提供跨平台的存储接口，如文件系统、配置信息和数据库。

#### 2.24 资源管理

> 有没有统一的资源管理接口？资源管理也是很麻烦的事情：比如图片，它可能存放在 flash 中，可能存放在文件系统中，也可能放在服务器上；对于普通屏和高清屏需要加载不同的文件；不同的语言也可能需要加载不同的文件；同一个软件在不同的系统上运行，可能要加载不同的格式，有的系统只能使用位图，有的系统可以使用 png/jpg；图片还需缓存，缓存还需要清理。所有这些东西，如果让应用程序来处理，那将是一场噩梦！

> 强大的资源管理器，可以屏蔽所有这些细节，让应用程序无需感知。比如，你需要"earth"这个图片，你无需关心它的位置和格式，无需关心屏幕密度和语言的影响，系统自动加载最佳的图片文件。

#### 2.25 事件处理流程

> 事件有没有区分 Bubbling 和 capturing 阶段？事件在不同阶段是否可以中止执行？是否有 pointer down abort 或 pointer down cancel 之类的事件？

#### 2.26 framebuffer

> 是否支持单 framebuffer？是否支持双 framebuffer？是否支持 3 framebuffer？是否支持 fragment framebuffer? 是否支持单色屏？是否能支持各种特殊的格式的 framebuffer? 是否支持 SPI 等特殊硬件的屏？

#### 2.27 光标

> 在非触摸屏的系统中，光标仍然是必不可少的功能。是否支持设置光标？是否支持根据当前的控件自动切换光标？是否支持根据当前的状态切换光标？

#### 2.28 窗口置顶

> 是否支持将指定窗口置顶？

#### 2.29 窗口管理

> 是否支持打开窗口时关闭当前窗口？是否支持将打开的窗口提到前台？是否可以关闭指定的窗口？是否支持回到 Home 窗口？是否可以设置窗口的关闭特性（唯一实例、禁止关闭、直接关闭和需要确认后关闭）? 对话框是否支持模态和非模态？

#### 2.30 基础库是否强大

> 是否提供了强大而且跨平台的基础库？特别是 C 语言开发，字符串、动态数组、链表、对象、事件发射器、定时器、字符串编码转换、文件、线程、互斥锁、信号量、时间、日期、动态库加载、共享内存和各种流的抽象都是非常有用的，如果提供一套稳定可靠的基础库，可以大大降低应用程序的开发成本。

#### 2.31 是否支持屏幕旋转

> 在没有 GPU 的情况下，屏幕旋转会大幅降低性能，应该尽量避免屏幕旋转。但是在项目早期，在买来的开发板上开发，确实可能有旋转的需求，如果 GUI 支持旋转，也是很方便的。

> 在 Android/iOS 上，有些应用横屏使用更加方便，对于一个跨平台的 GUI，支持动态旋转无疑也是加分项。

## 3. 性能

#### 3.1 高效的算法

> 是否支持脏矩形算法、3 framebuffer 和 二进制格式。开发时使用 XML 方便程序员修改，运行时使用高效二进制格式提高运行效率。

#### 3.2 2D 硬件加速

> 是否支持常见的加速接口，如 STM32 的 DMA2D 和 NXP 的 PXP。厂家是否可以扩展自己的加速接口。

#### 3.3 3D 硬件加速

> 是否支持 OpenGL、DirectX、Vulkan 和 Metal 等。

#### 3.4 低端平台

> 最低能支持什么样的硬件平台？功能强大体积通常比较大，这对 GUI 的可配置性是一个极大的考验。

#### 3.5 启动时间

> 1 秒启动？5 秒启动？还要等半分钟？

## 4. 国际化

#### 4.1 Unicode。

> 是否支持 UTF-8 和 UTF-16 编码？

#### 4.2 多国语言输入法。

> 是否支持 T9 输入法？是否可以支持新的输入法？

#### 4.3 字符串翻译。

> 是否支持字符串翻译？是否支持实时切换语言（不需重启）？

#### 4.4 图片翻译。

> 是否支持图片翻译（既切换语言时，自动切换某些图片）？

#### 4.5 文字双向排版。

> 是否支持阿拉伯文字的双向排版？

#### 4.6 编码转换函数。

> 是否提供的跨平台的编码转换函数？

## 5 软件质量

#### 5.1 单元测试

> 是否有完整的单元测试？单元测试是否全部通过？

#### 5.2 内存耗尽处理流程

> 内存耗尽时是直接崩溃？还是让应用程序能优雅的退出？

#### 5.3 内存泄露检查机制

> 是否有内存泄露检查机制？是否能用 valgrind 进行内存泄露和溢出检查？

#### 5.4 代码静态检查。

> 是否通过了 [cppcheck](http://cppcheck.sourceforge.net/)、[infer](https://github.com/facebook/infer) 或其它静态检查工具的检查？

#### 5.5 事件录制和重放功能

> 是否可以录制用户操作的事件，并通过重放进行压力测试？

#### 5.6 Appuim 进行自动测试

>  是否支持 Appuim，通过 javascript 等脚本自动化集成测试？
