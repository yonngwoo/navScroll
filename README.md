navScroll
=========

<p>navScroll 滚动到指定容器</p>
<p><strong>Demo 预览：</strong>http://demo.webjyh.com/navScroll/</p>

<blockquote>
	<p>=== V1.2.0 ===</p>
	<ul>
		<li>1.修正某个导航不需要 navScroll 功能。</li>
		<li>2.如本页中 导航中的 M.J 一样。链接功能依旧保持。</li>
	</ul>
	
	<p>=== V1.1.0 ===</p>
	<ul>
		<li>1.增加scroll事件，根据 scroll 在 box 的位置给 nav 添加 class</li>
		<li>1.调用方法改动</li>
	</ul>
</blockquote>

<h4>navScroll 该如何使用呢？</h4>
<p>头部引用JS文件 (不需要任何JS库，直接引用即可)</p>
<pre>
&lt;script type="text/javascript" src="navScroll.js"&gt;&lt;/script&gt;
</pre>

<h4>初始化导航HTML (结构必须为这样 大家直接Copy吧)</h4>
<pre>
&lt;ul class="navigation clearfix" id="navigation"&gt;
	&lt;li&gt;&lt;a href="#box-1" class="current"&gt;home&lt;/a&gt;&lt;/li&gt;
	&lt;li&gt;&lt;a href="#box-2"&gt;categories&lt;/a&gt;&lt;/li&gt;
	&lt;li&gt;&lt;a href="#box-3"&gt;about&lt;/a&gt;&lt;/li&gt;
	&lt;li&gt;&lt;a href="#box-4"&gt;full Width Page&lt;/a&gt;&lt;/li&gt;
	&lt;li&gt;&lt;a href="#box-5"&gt;Most Loved Posts&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
</pre>

<blockquote>
PS: HTML 结构中的 a 链接中 href 的值就是你所对应要跳转到 Box 的位置，这跟锚点的做法一样。<br />
例如：<br />
href="#box-1" 值为 #box-1 则 对应的 Box就是 &lt;div id="box-1"&gt;&lt;/div&gt;
点击之后 会跳转到 id为Box-1的位置。
</blockquote>

<h4>附带功能：调整布局</h4>
<blockquote>
PS: 此功能是用于当窗口宽度小于容器宽度，内容居中显示。只适合最外成容器ID。<br />
例如：<br />
外容器 id="wrap-main" 宽度定义为 1200px 当窗口小于1200 内容会以中间显示，裁剪两边的，有点类似于 CSS 中 margin:0px auto;效果 <br />
在设置此效果时，需要将 body 设置以下CSS body { overflow-x:hidden; } 才会有效果
</blockquote>

<h4>导航参数 fixPx</h4>
<blockquote>
PS: 此功能是用于在导航使用绝对定位且在窗口上方，导致点击Box后，Box到达位置后，容器头部的内容被导航遮挡。所以添加此参数。默认参数为0。<br />
例如：<br />
此参数添写多少合适呢，就是填写你导航容器的高度，这样Box到达位置后，不会被导航遮住。 因 IE 6下 position:fixed; 有问题，所以此功能在IE6下有可能会产生错位。
</blockquote>

<h4>初始化JS</h4>
<pre>
&lt;script type="text/javascript"&gt;
new navScroll({
    resizeWrap : {           //调整布局功能，不需要此功能，此代码块可以删除
        wrap : 'wrap',       //外容器ID
        maxWidth : 600       //窗口小于多少PX调整布局，不需要此功能，参数可以删除
    },
    nav : {                  //导航跳转功能，不需要可以删除此代码块
        id : 'navigation',   //点击跳转到容器的导航ID 请把 ID 设置给 UL 
        current : 'current', //默认点击A链接后，默认样式名
        speed : 25,          //动画执行速度，越小则越快。反之，越慢。
        fixPx :40            //在导航使用绝对定位且在窗口上方，容器与导航的差,默认为0
    }
});
&lt;script&gt;
</pre>
