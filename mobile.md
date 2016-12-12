#移动端适配方法（adaptation）
1.百分比(流式布局)

 对一个元素的比例没有特殊要求的时候,可以用百分比来进行布局

2.响应式

工作大，维护性难

3.viewport

 通过动态的设置窗口比例,使得我们可以使用原图大小来进行布局这个方法简单粗暴，又高效,但是使用过程中反应缩放会导致有些页面元素会模糊

4.弹性盒模型

   适合对一行有多个内容或有多行内容来进行批量处理的情况

5.rem

rem（font size of the root element）是指相对于根元素的字体大小的单位
#flex 弹性布局盒模型

##设置弹性盒模型
 
1.display:flex (新版)

2.display:-webkit-box; (旧版)

## flex容器

 1.项目排列的方向

1.1 row 从左到右排列(默认)

1.2 row-reverse 从右到左

1.3 column 从上到下

1.4 column-reverse 从下到上

      flex-direction: row | row-reverse |column |column-reverse
      horizontal 水平方向
      vertical 垂直方向
      -webkit-box-orient:horizontal | vertical
      normal 顺序正常
      reverse 反向
      -webkit-box-direction:normal |reverse

2.项目包裹方式

   2.1 nowrap 不换行(默认)

    2.2 wrap 容器如果不足以放下项目,自动换行到一下行 

                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  2.3 wrap-reverse 容器如果不足以放下项目,  制动换行到上一行

  flex-wrap:nowrap | wrap | wrap-reverse 
3.项目水平对齐方式
  3.1 flex-start 左对齐
  3.2 flex-end 右对齐
  3.3 center 中对齐
  3.4 space-between 两端对齐
  3.5 space-around 每个项目两侧的间隔相等
    justify-content:flex-start | flex-end | center | space-between | space-around
    start 左对齐
    end 右对齐
    center 居中
    justiry 两队对齐
   -webkit-box-pack: start | end |center |justify 
4.项目的垂直对齐方式
   4.1 flex-start 顶对齐
   4.2 flex-end 底对齐
   4.3 center 垂直居中
 4.4 baseline 项目的第一行文字的基线对齐
   4.5 stretch 如果项目未设置高度,占满整个容器高度
  align-items:flex-start | flex-end | center | baseline | stretch        
  旧版 
start 顶对齐

     end 底对齐
     center 垂直居中
  -webkit-box-align:start | end |center
5.多行对齐方式

   5.1 flex-start 左对齐

   5.2 flex-end 右对齐

   5.3 center 中对齐

   5.4 space-between 两端对齐

   5.5 space-around 每个项目距离相同

   5.6 stretch 占满容器高度(拉伸)

   align-content:  flex-start | flex-end | center | space-between | space-around | stretch

##flex项目(列表)

1.项目排序

   1.1 项目的排序,数字越小越靠前,默认值为0 ,接收负值

      order:<int>  

旧版：

项目的排序,数字越小越靠前,默认值为1 ,将0或负数转为1

-webkit-box-ordinal-group:

2.项目占比(放大)

   2.1 所占栅格比例,默认为零 项目的尺寸=容器的尺寸/总栅格数*当前栅格数

     flex-grow:<int>

旧版：

老版弹性布局设置项目栅格

  -webkit-box-flex : <int>  
  
3.项目占比(缩小)

  3.1 所占栅格比例,默认为1

  flex--shrink:<int>

4.项目所占空间大小

  4.1 可以设置项目的大小 类似于 width\height属性

  flex-basis:<size> | auto

5.项目自己的对齐方式 优先级高于容器的 align-items

  align-self: auto | flex-start | flex-end | center |   baseline | stretch;     

#移动端布局常见问题

1.横竖屏限制问题

    <meta name="x5-orientation" content="portrait | landscape" />  只支持x5内核

    <meta name="screen-orientation" content="portrait">   只支持uc浏览器

2.全屏限制问题

    <meta name="x5-fullscreen" content="true" />   只支持x5内核

    <meta name="full-screen" content="yes">   只支持uc浏览器

3.禁止识别电话号码和邮箱

    <meta name="format-detection" content="telephone=no, email=no" />

    禁止识别后页面当中所有的邮箱和电话将不会识别,如果有特殊需求,要配合一下代码实现

    <a href="tel:110">请拨打电话110</a>

     <a href="qq@.com">请发送邮件qq@.com</a>   
     
4.消除链接\表单\按钮 默认背景

     -webkit-tap-highlight-color: rgba(0, 0, 0, 0);

5.消除按钮圆角

     -webkit-appearance: none;

6.移动端字体

    ios系统

    默认中文字体是Heiti SC

    默认英文字体是Helvetica

    默认数字字体是HelveticaNeue

    无微软雅黑字体

7.android 系统

    默认中文字体是Droidsansfallback
  
    默认英文和数字字体是Droid Sans

    无微软雅黑字体
8.winphone 系统

    Dengxian(方正等线体)

    默认英文和数字字体是Segoe

     无微软雅黑字体
结论

     1.各个手机系统有自己的默认字体，且都不支持微软雅黑

     2.如无特殊需求，手机端无需定义中文字体，使用系统默认

     3.英文字体和数字字体可使用 Helvetica ，三种系统都支持

     body{font-family:Helvetica;}
9.禁止用户设置字体大小

     -webkit-text-size-adjust:100%  
10.禁止文字选中

     -webkit-user-select:none  //安卓不支持

    font boosting 移动端设备为了使用户能看清楚大批量的字体,会自动对字体进行放大,但是只要指定了容器的高度,就能解决

    p{max-height:9999999px}     
 
11.固定定位问题

   解决：
    用绝对定位来代替固定定位

    用容器自己的的滚动条来代替浏览器上的滚动条

    在有的手机上面，拖动滚动条的时候，会出现卡顿的现象


12.移动端环境搭建

    利用 chrome 浏览器 deviceToolbar 来调试移动端页面的尺寸

     利用本地服务器创建端口,进行真机调试.

    利用hbuilder等工具进行虚拟机调试   
 
#移动端视口(viewport)问题
  
    viewport就是设备的屏幕上能用来显示我们的网页的那一块区域
 
    移动设备上一般存在3种视口

##layout viewport 默认的布局视口

     移动端设备的屏幕不是很宽,但是又想完整的呈现各种页面(pc端的页面),所以移动端浏览器把视口默认的定义为一个  较宽的值,一般为980px

     可以通过 document.documentElement.clientWidth 获取到

     但是一般布局视口都会比我们的屏幕大,所以会出现滚动条,用户体验很不友好,于是出现了 visual viewport

##visual viewport 视觉视口

    一般来说视觉视口,就是我们移动设备屏幕的大小window.innerWidth ,我们都知道移动设备的屏幕尺寸小于桌面端

     的屏幕尺寸,那么要想在有限的窗口内表达更多的像素

    那么移动端的设备就必须要通过物理手段来解决,在有限的屏幕内显示更多的像素点,于是就有了各种高清屏,比方说2k

    \4k\视网膜屏等,这些设备的dpi很高

    dpi指的就是屏幕像素密度,我们也叫做物理像素,比方说:安卓分为ldpi、mdpi、hdpi、xhdpi等不同的等级

     而css所表示的一个像素我们叫做独立像素 像素比: devicePixelRatio = 物理像素 / 独立像素 可以通过 

    window.devicePixelRatio 获取,不过有些浏览器不支持

    在有的浏览器里面会用物理像素表示独立像素,有的浏览器里面会用独立像素单独表示,就会出现要不然很小,要不然很大的情况
    如何解决这个问题:浏览器帮我们创建了一个理想视觉窗口,让我们可以自己定义该视口有多大,并且强制用独立像素来表达
##ideal viewport 理想视口

    理想视口并没有一个固定的尺寸,那么我们就能将浏览器的视口,设置我们任意想要的大小,并且强制用独立像素来表达

     诉求.其实就是用将布局视口设置为理想视口

    一般来说我们会将理想视口,设置为我们屏幕的大小,这样更符合用户的使用习惯和视觉习惯

    但是移动设备的屏幕千差万别,我们会通过html5给我提供的meta标签来进行设置

    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0"> 

     1.width=| device-width 设置布局视口的宽度

      2.initial-scale= 页面的初始缩放值

      3.minimum-scale= 允许用户的最小缩放值

      4.maximum-scale= 允许用户的最大缩放值

      5.height= 这个属性对我们并不重要，很少使用

      6.user-scalable=no | yes 是否允许用户缩放 (iOS10不支持) 
    









