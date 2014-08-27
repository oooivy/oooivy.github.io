
<h1 class = "postTitle">L6.盒模型总结</h1>
		<div class="clear"></div>
		<div class="postBody">
			<div id="cnblogs_post_body"><p>&nbsp;</p>
<p>html元素可以分别归为顶级(top-level)元素,块级(block-level)元素和内联(inline)元素.<sup>[3]</sup></p>
<ol>
<li>Block-level element: 指能够独立存在, 一般的块级元素之间以换行(如一个段落结束后另起一行)分隔. 常用的块级元素包括: p, h1~h6, div, ul等;</li>
<li>Inline element: 指依附其他块级元素存在, 紧接于被联元素之间显示, 而不换行. 常用的内联元素包括: img, span, li, br等;</li>
<li>Top-level element: 包括html, body, frameset, 表现如Block-level element, 属于高级块级元素.</li>
</ol>
<p>Box model：由content(内容), padding, border(边框), margin组成. 典型的盒模型如下图所示:</p>
<p><img src="http://images.cnitblog.com/i/551450/201406/170958117231507.jpg" alt="" /></p>
<p>平面图如下：</p>
<p><img src="http://wangtengteng.qiniudn.com/imgbox.bmp" alt="" /></p>
<h3 id="the-lsquo"><span class="secno">1、盒类型</span></h3>
<p><span class="secno">盒类型取决于display的属性in combination with &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#float">float</a>&rsquo; and &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#position">position</a>&rsquo;。</span></p>
<p><span class="secno">display的属性值 ：inline | block | inline-block | list-item | run-in | compact | table | inline-table | table-row-group | table-header-group | table-footer-group | table-row | table-column-group | table-column | table-cell | table-caption | ruby | ruby-base | ruby-text | ruby-base-group | ruby-text-group |<var><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#lttemplategt">&lt;template&gt;</a></var>| none</span></p>
<p>1.1&nbsp;display属性的说明值：</p>
<p>（1）display常见属性值：</p>
<p align="left"><strong><em>inline</em></strong><em>&nbsp;</em>&nbsp;创建inline box</p>
<p align="left"><strong><em>block &nbsp;</em></strong>创建block box</p>
<p align="left"><strong><em><strong><em>none</em></strong></em><strong>&nbsp;&nbsp;</strong></strong>不创建box,有别于visibility:hidden。visibility:hidden会创建box,只是不显示。</p>
<p align="left"><strong><em>inline-block</em></strong></p>
<p align="left">创建的box本身是inline box,而内部的由block box组成。</p>
<p align="left">（2）display不常见属性值：</p>
<p align="left"><span style="font-size: 12px;"><strong><em>list-item</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">One or more block boxes and one marker box. Marker boxes are defined in the Lists module&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3LIST">[CSS3LIST]</a>.&nbsp;If the Lists module is not ready, define the position of the marker and the list-style property here? Or refer to CSS&nbsp;2.1 instead?</span></p>
<p align="left"><span style="font-size: 12px;"><strong><em>run-in</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">Either block or inline boxes, depending on context (see&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#run-in-boxes">Run-in boxes</a>). Properties apply to run-in boxes based on their final status (<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#inline-level">inline-level</a>&nbsp;or&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-level">block-level</a>).</span></p>
<p align="left"><span style="font-size: 12px;"><strong><em>compact</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">Either block boxes or a marker box, depending on context (see&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#compact-boxes">Compact boxes</a>). Properties apply to compact boxes based on their final status.</span></p>
<p align="left"><span style="font-size: 12px;"><strong><em>table</em></strong><strong>,</strong><strong>&nbsp;<em>inline-table</em></strong><strong>,</strong><strong>&nbsp;<em>table-row-group</em></strong><strong>,</strong><strong>&nbsp;<em>table-header-group</em></strong><strong>,</strong><strong>&nbsp;<em>table-footer-group</em></strong><strong>,</strong><strong>&nbsp;<em>table-row</em></strong><strong>,</strong><strong>&nbsp;<em>table-column-group</em></strong><strong>,</strong><strong>&nbsp;<em>table-column</em></strong><strong>,</strong><strong>&nbsp;<em>table-cell</em></strong><strong>,</strong><strong>&nbsp;<em>table-caption</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">See the Tables module&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3TBL">[CSS3TBL]</a>.</span></p>
<p align="left"><span style="font-size: 12px;"><strong><em>ruby</em></strong><strong>,</strong><strong>&nbsp;<em>ruby-base</em></strong><strong>,</strong><strong>&nbsp;<em>ruby-text</em></strong><strong>,</strong><strong>&nbsp;<em>ruby-base-group</em></strong><strong>,</strong><strong>&nbsp;<em>ruby-text-group</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">See the Ruby module&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3RUBY">[CSS3RUBY]</a>.</span></p>
<p align="left"><span style="font-size: 12px;"><strong><em>&lt;template&gt;</em></strong></span></p>
<p align="left"><span style="font-size: 12px;">See the Advanced Layout module&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3LAYOUT">[CSS3LAYOUT]</a>.</span></p>
<p align="left">1.2 计算值</p>
<table class="equiv-table">
<thead>
<tr><th>Specified value</th><th>Computed value</th></tr>
</thead>
<tbody>
<tr>
<td>inline-table</td>
<td>table</td>
</tr>
<tr>
<td>inline, run-in, table-row-group, table-column, table-column-group, table-header-group, table-footer-group, table-row, table-cell, table-caption, inline-block</td>
<td>block</td>
</tr>
<tr>
<td>others</td>
<td>same as specified<br /><br /></td>






</tr>






</tbody>





</table>
<p align="left">1.3&nbsp;<span class="secno">完整规则：</span></p>
<ol>
<li>If &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; is &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#none0">none</a></code>&rsquo;, then &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#float">float</a>&rsquo; and &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#position">position</a>&rsquo; do not apply.</li>
<li>此外，若 &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#position">position</a>&rsquo;值不为 &lsquo;<code class="css">static</code>&rsquo; &nbsp;&lsquo;<code class="css">relative</code>&rsquo;（此时，float 不起作用）, &nbsp;&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; 根据（1.2）的表格计算.</li>
<li>此外，若float 不为 &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#none0">none</a></code>&rsquo;,&nbsp;&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; 根据（1.2）的表格计算.</li>
<li>此外，若元素为根元素,&nbsp;&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; 根据（1.2）的表格计算.</li>
<li>此外, &nbsp;&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; 的计算值与说明值（1.1）一致.</li>




</ol>
<h3><span style="font-size: 15px;"><strong>&nbsp;2、块级box、包含块、流、匿名box&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-level0">Block-level boxes, containing blocks, flows and anonymous boxes</a></strong></span></h3>
<p>&nbsp;（1）A&nbsp;<dfn id="block-level">block-level</dfn>&nbsp;box&nbsp;</p>
<p>（2）An&nbsp;<dfn id="inline-level">inline-level</dfn>&nbsp;box&nbsp;</p>
<p>（3）An&nbsp;<dfn id="anonymous">anonymous box</dfn></p>
<p>（4）The&nbsp;<dfn id="containing">containing block</dfn>&nbsp;of a box&nbsp;</p>
<p>包含块（containing block）的定义：元素盒子的位置和大小通常需要通过一个确定的矩形来计算，这个矩形就是包含块。</p>
<p>这个矩形除了size和positon外还有&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#direction">direction</a>&rsquo; 和 &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo;属性。</p>
<p>包含块定义如下：</p>
<p>1）根元素的包含块是一个被称为原始包含块（initial containing block）的矩形。它由视口确定，对于分页媒体来说就是页区域。它的direction属性时和根元素的一样<br />2）对于其他元素，如果元素的position是relative或static，包含块由其最近的块级祖先的内边距（content edge）来确定<br />如果元素时position:fixed，那么包含块就是连续媒体的视口或是分页媒体的页区域<br />如果元素的position属性时absolute，包含那块将根据最近的position属性为非static的祖先元素来确定，有如下规则 - 当那个祖先元素是一个内联元素时，包含块需要根据祖先元素的direction属性来确定 - 如果direction是ltr，那么包含块的左上顶点将是祖先元素的第一个盒子的左上顶点，而包含块的右下顶点将是祖先元素最后一个盒子的右下顶点 - 如果direction是rtl，那么包含块的右上顶点将是祖先元素的第一个盒子的右上顶点，而包含块的左下顶点将是祖先元素最后一个盒子的左下顶点<br />如果祖先元素是块状元素，那么它的包含块将是这个祖先元素的padding edge<br />如果没有这么一个祖先元素，则包含块就是原始包含块</p>
<p>（4）A&nbsp;<dfn id="flow-root">flow root</dfn>&nbsp;</p>
<p>是一个满足以下条件的盒子:</p>
<ul>
<li>The value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#float">float</a>&rsquo; is not &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#none0">none</a></code>&rsquo;.</li>
<li>The&nbsp;<em><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#used-value.">used value</a></em>&nbsp;of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#overflow0">overflow</a>&rsquo; is not &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#visible0">visible</a></code>&rsquo;.</li>
<li>The value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; is &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#table-cell">table-cell</a></code>&rsquo;, &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#table-caption">table-caption</a></code>&rsquo; (see&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3TBL" rel="biblioentry">[CSS3TBL]</a>), &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#inline-block">inline-block</a></code>&rsquo; or &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#inline-table">inline-table</a></code>&rsquo;.</li>
<li>The value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#position">position</a>&rsquo; is neither &lsquo;<code class="css">static</code>&rsquo; nor &lsquo;<code class="css">relative</code>&rsquo; (see&nbsp;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#CSS3POS" rel="biblioentry">[CSS3POS]</a>).</li>
<li>The value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo; is &lsquo;<code class="css">lr</code>&rsquo; or &lsquo;<code class="css">rl</code>&rsquo; and the value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo; of its parent box is &lsquo;<code class="css">tb</code>&rsquo;</li>
<li>The value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo; is &lsquo;<code class="css">tb</code>&rsquo; and the value of &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo; of its parent box is &lsquo;<code class="css">lr</code>&rsquo; or &lsquo;<code class="css">rl</code>&rsquo;.</li>




</ul>
<p>&lsquo;<code class="css">display: inline</code>&rsquo; 的元素不会是flow root。但是&nbsp;flow root不一定是块级元素，它可以是&lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#inline-block">inline-block</a></code>&rsquo; 。（即：它可能本身是inline level box,它的子元素是块级block level box）</p>
<p>css2中的定义与此处（css3）不一样：A flow root is called &ldquo;an element that establishes a new formatting context.&rdquo; &nbsp;格式化上下文（formatting context）</p>
<p><strong>（5）The&nbsp;<dfn id="flow">flow</dfn>&nbsp;(a.k.a.&nbsp;<dfn id="normal">normal flow</dfn>)&nbsp;普通流</strong></p>
<p>给定的flow root的普通流是一系列的盒子。</p>
<p>A box belongs to the flow if:</p>
<ol>
<li>The used value of its &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#display">display</a>&rsquo; is &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block">block</a></code>&rsquo;, &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#list-item">list-item</a></code>&rsquo;, &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#table">table</a></code>&rsquo; or&nbsp;<var><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#lttemplategt">&lt;template&gt;</a></var>.</li>
<li>The used value of its &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#float">float</a>&rsquo; is &lsquo;<code class="css"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#none0">none</a></code>&rsquo;.</li>
<li>The used value of its &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#position">position</a>&rsquo; is &lsquo;<code class="css">static</code>&rsquo; or &lsquo;<code class="css">relative</code>&rsquo;.</li>
<li>It is either a child of the flow root or a child of a box that belong to the flow.</li>




</ol>
<p>文档流中的盒子，会在flow root元素中按照文档顺序和&lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#block-progression">block-progression</a>&rsquo; 定义的方向一个接一个排布。它们的位置由margins决定。margins可能和它们的包含块的边界发生<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#collapsing-margins">Collapsing </a><span style="text-decoration: underline;">。</span>&nbsp;&nbsp;More precisely: Each box's left and right margin edges coincide with the left and right content edges of its containing block (if the flow root is &lsquo;<code class="css">tb</code>&rsquo;), or its top and bottom margin edges coincide with the top and bottom content edges of its containing block (if the flow root is &lsquo;<code class="css">rl</code>&rsquo; or &lsquo;<code class="css">lr</code>&rsquo;).</p>
<div class="cnblogs_code">
<pre><span style="color: #000000;">For example, the fragment
</span><span style="color: #0000ff;">&lt;</span><span style="color: #800000;">div </span><span style="color: #ff0000;">class</span><span style="color: #0000ff;">=sidebar</span><span style="color: #0000ff;">&gt;</span>
 <span style="color: #0000ff;">&lt;</span><span style="color: #800000;">p</span><span style="color: #0000ff;">&gt;</span><span style="color: #000000;">Text in a sidebar.
 </span><span style="color: #0000ff;">&lt;</span><span style="color: #800000;">p</span><span style="color: #0000ff;">&gt;</span><span style="color: #000000;">Here is quote:
 </span><span style="color: #0000ff;">&lt;</span><span style="color: #800000;">blockquote </span><span style="color: #ff0000;">lang</span><span style="color: #0000ff;">=ja</span><span style="color: #0000ff;">&gt;</span>
  <span style="color: #0000ff;">&lt;</span><span style="color: #800000;">p</span><span style="color: #0000ff;">&gt;</span><span style="color: #000000;">...
 </span><span style="color: #0000ff;">&lt;/</span><span style="color: #800000;">blockquote</span><span style="color: #0000ff;">&gt;</span>
 <span style="color: #0000ff;">&lt;</span><span style="color: #800000;">p</span><span style="color: #0000ff;">&gt;</span><span style="color: #000000;">Etc. etc.
</span><span style="color: #0000ff;">&lt;/</span><span style="color: #800000;">div</span><span style="color: #0000ff;">&gt;</span><span style="color: #000000;"> 
with the style
　　div.sidebar { block-progression: tb; float: left }
　　blockquote[lang|=ja] { block-progression: rl; height: 10em }
defines two flows:
　　The div is a flow root, because it floats. Its flow consist of the 1st, 2nd and 4th p and the blockquote.
　　The blockquote is vertical, while its parent is horizontal and it is thus a flow root. Its flow is formed by the 3rd p.</span></pre>
</div>
<h3 id="the-padding"><span class="secno">3. padding</span></h3>
<p><span class="secno">[&nbsp;<var><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#ltlengthgt">&lt;length&gt;</a></var>&nbsp;|&nbsp;<var>&lt;percentage&gt;</var>&nbsp;] padding值不能为负</span></p>
<p><span class="secno"><dfn id="padding-top">padding-top</dfn>&nbsp;,&nbsp;<dfn id="padding-right">padding-right</dfn>,&nbsp;<dfn id="padding-bottom">padding-bottom</dfn>,&nbsp;<dfn id="padding-left">padding-left 的缩写</dfn></span></p>
<p><span class="secno">注意： &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-top">padding-top</a>&rsquo; and &lsquo;<a class="property" href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-bottom">padding-bottom</a>&rsquo; 的百分值是相对于包含块的宽度的（&nbsp;<em><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#width">width</a></em>&nbsp;of the containing block), 不是高度 (至少在horizontal flow中;在 vertical flow 中它们是相对于高度的)。</span></p>
<h3 id="the-padding"><span class="secno">4. margin</span></h3>
<p><span class="secno">[&nbsp;<var><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#ltlengthgt">&lt;length&gt;</a></var>&nbsp;|&nbsp;<var>&lt;percentage&gt;</var>&nbsp;] margin值可能为负</span></p>
<p><span class="secno"><dfn id="padding-left"><dfn id="margin-top">margin-top</dfn>&nbsp;,&nbsp;<dfn id="margin-right">margin-right</dfn>,&nbsp;<dfn id="margin-bottom">margin-bottom</dfn>,&nbsp;<dfn id="margin-left">margin-left</dfn>&nbsp;的缩写</dfn></span></p>
<h3 id="collapsing-margins"><span class="secno">5.&nbsp;Collapsing margins （http://www.cnblogs.com/guozhiguoli/p/3791466.html）</span></h3>
<h3 id="collapsing-margins"><span class="secno">6.&nbsp;宽度、高度的计算 (对应标准第9节&nbsp;Calculating widths, heights and margins)</span></h3>
<p><span class="secno"><var>&lt;length&gt;</var>&nbsp;|&nbsp;<var>&lt;percentage&gt;</var>&nbsp;| auto</span></p>
<p><span class="secno">不同的浏览器实现有差别。标准里面说当我们在css中设计一个块级元素的width和height属性时比如.box{width ：100px; height:100px}时，其中的width 和height仅仅是对content部分设置的，而不是内容，内边距，边框的总和（但在IE的早期版本包括IE6中，盒子模型的width和height却恰恰是这样定义的，尽管符合人们思考的逻辑，但是不符合规范）</span></p>
<p>&nbsp;</p>
<p>计算宽度和高度：相关属性min-width,max-width,width; min-height,max-height,height。先不管min与max，按规则计算出width或height的值tentative used width(/height)。然后使tentative used width界于min和max之间。</p>
<p>加入宽高比后的计算规则：</p>
<p>总的来说，就是不超过最大最小值的限制，先确定width/height，同时尽量保持ratio，保持不了的取按最大最小值。</p>
<table border="0" cellpadding="0">
<thead>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><strong><span lang="EN-US">Constraint violation</span></strong></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><strong><span lang="EN-US">Resolved width</span></strong></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><strong><span lang="EN-US">Resolved height</span></strong></p>
</td>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">none</span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">w</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">h</span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">w&nbsp;&gt;&nbsp;max-width &nbsp;</span></em><span lang="EN-US">（没列出来，默认h&lt;max-height，所以计算后不用考虑是高度是否超过最大值<span lang="EN-US">）</span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-width" shape="rect" target="_blank">max-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">max(max-width&nbsp;*&nbsp;h/w, min-height)</span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">w&nbsp;&lt;&nbsp;min-width</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-width" shape="rect" target="_blank">min-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">min(min-width&nbsp;*&nbsp;h/w, max-height)</span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">h&nbsp;&gt;&nbsp;max-height</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">max(max-height&nbsp;*&nbsp;w/h, min-width)</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-height" shape="rect" target="_blank">max-height</a></span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">h&nbsp;&lt;&nbsp;min-height</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">min(min-height&nbsp;*&nbsp;w/h, max-width)</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-height" shape="rect" target="_blank">min-height</a></span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&gt;&nbsp;max-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&gt;&nbsp;max-height</span></em><span lang="EN-US">), where (<em><span lang="EN-US">max-width/w&nbsp;&le;&nbsp;max-height/h</span></em><span lang="EN-US">)</span></span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-width" shape="rect" target="_blank">max-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">max(min-height, max-width&nbsp;*&nbsp;h/w)</span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&gt;&nbsp;max-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&gt;&nbsp;max-height</span></em><span lang="EN-US">), where (<em><span lang="EN-US">max-width/w&nbsp;&gt;&nbsp;max-height/h</span></em><span lang="EN-US">)</span></span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">max(min-width, max-height&nbsp;*&nbsp;w/h)</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-height" shape="rect" target="_blank">max-height</a></span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&lt;&nbsp;min-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&lt;&nbsp;min-height</span></em><span lang="EN-US">), where (<em><span lang="EN-US">min-width/w&nbsp;&le;&nbsp;min-height/h</span></em><span lang="EN-US">)</span></span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">min(max-width, min-height&nbsp;*&nbsp;w/h)</span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-height" shape="rect" target="_blank">min-height</a></span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&lt;&nbsp;min-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&lt;&nbsp;min-height</span></em><span lang="EN-US">), where (<em><span lang="EN-US">min-width/w&nbsp;&gt;&nbsp;min-height/h</span></em><span lang="EN-US">)</span></span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-width" shape="rect" target="_blank">min-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US">min(max-height, min-width&nbsp;*&nbsp;h/w)</span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&lt;&nbsp;min-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&gt;&nbsp;max-height</span></em><span lang="EN-US">)</span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-width" shape="rect" target="_blank">min-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-height" shape="rect" target="_blank">max-height</a></span></em></p>
</td>
</tr>
<tr>
<td rowspan="1" colspan="1">
<p align="left"><span lang="EN-US">(<em><span lang="EN-US">w&nbsp;&gt;&nbsp;max-width</span></em><span lang="EN-US">) and (<em><span lang="EN-US">h&nbsp;&lt;&nbsp;min-height</span></em><span lang="EN-US">)</span></span></span></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#max-width" shape="rect" target="_blank">max-width</a></span></em></p>
</td>
<td rowspan="1" colspan="1">
<p align="left"><em><span lang="EN-US"><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#min-height" shape="rect" target="_blank">min-height</a></span></em></p>
</td>
</tr>
</tbody>
</table>
<div>接下来，分类陈述不同情况下的width和height: （不知道这一大堆都用在什么地方&hellip;&hellip;）</div>
<div>
<h3><span style="font-size: 14px;">9.1.&nbsp;Inline, non-replaced elements</span></h3>
<div><span style="font-size: 14px;">The &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#width" shape="rect" target="_blank">width</a>&rsquo; and &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#height" shape="rect" target="_blank">height</a>&rsquo; properties do not apply.</span></div>
<div>
<h3><span style="font-size: 14px;">9.2.&nbsp;Inline or floating, replaced elements</span></h3>
<div><span style="font-size: 14px;">&lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-left" shape="rect" target="_blank">margin-left</a>&rsquo;, &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-right" shape="rect" target="_blank">margin-right</a>&rsquo;, &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-top" shape="rect" target="_blank">margin-top</a>&rsquo; and &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-bottom" shape="rect" target="_blank">margin-bottom</a>&rsquo;为计算值。宽高参考ratio进行计算，若都是auto且都没有intrinsic值(固有宽度、固有高度)，根据9.4的计算公式计算宽度，再根据ration计算高度。</span></div>
<div>
<h3><span style="font-size: 14px;">9.3.&nbsp;Block-level, non-replaced elements in normal flow when &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#overflow0" shape="rect" target="_blank">overflow</a>&rsquo; computes to &lsquo;<code><a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#visible0" shape="rect" target="_blank">visible</a></code>&rsquo;</span></h3>
<div>
<h3><span style="font-size: 14px;">&lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-left" shape="rect" target="_blank">margin-left</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#border-left-width" shape="rect" target="_blank">border-left-width</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-left" shape="rect" target="_blank">padding-left</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#width" shape="rect" target="_blank">width</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-right" shape="rect" target="_blank">padding-right</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#border-right-width" shape="rect" target="_blank">border-right-width</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-right" shape="rect" target="_blank">margin-right</a>&rsquo; + scrollbar width (if any) = width of containing block</span></h3>
</div>
<div><span style="font-size: 14px;">If &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#width" shape="rect" target="_blank">width</a>&rsquo; is not &lsquo;<code>auto</code>&rsquo; and &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#border-left-width" shape="rect" target="_blank">border-left-width</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-left" shape="rect" target="_blank">padding-left</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#width" shape="rect" target="_blank">width</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#padding-right" shape="rect" target="_blank">padding-right</a>&rsquo; + &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#border-right-width" shape="rect" target="_blank">border-right-width</a>&rsquo; + scrollbar width (if any) (plus any of &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-left" shape="rect" target="_blank">margin-left</a>&rsquo; or &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-right" shape="rect" target="_blank">margin-right</a>&rsquo; that are not &lsquo;<code>auto</code>&rsquo;) is larger than the width of the containing block, then any &lsquo;<code>auto</code>&rsquo; values for &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-left" shape="rect" target="_blank">margin-left</a>&rsquo; or &lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#margin-right" shape="rect" target="_blank">margin-right</a>&rsquo; are, for the following rules, treated as zero.&nbsp;We should drop this paragraph. It causes blocks that are wider than their parent not to be centered (unlike blocks that are narrower), which looks strange.</span></div>
<div><span style="font-size: 14px;">&ldquo;over-constrained&rdquo;的时候会有一个属性与它的计算值不一样。若&lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#direction" shape="rect" target="_blank">direction</a>&rsquo;='ltr'，则margin-right值被忽略。反之亦然。</span></div>
<div>
<h3><span style="font-size: 14px;">9.4.&nbsp;Other block-level, non-replaced elements in normal flow</span></h3>
</div>
<div>
<h3><span style="font-size: 14px;">9.5.&nbsp;&lsquo;<a href="http://www.w3.org/TR/2007/WD-css3-box-20070809/#inline-block" shape="rect" target="_blank">Inline-block</a>&rsquo; or floating, non-replaced elements</span></h3>
<p>&nbsp;</p>
<h3 id="collapsing-margins"><span class="secno">7. 盒子的定位<sup>[4]</sup></span></h3>
<p>CSS中一个盒子的定位可以通过如下三种定位模式：&nbsp;</p>
<ol>
<li>文档流：文档流包括块级元素的块级格式和内联元素的内联格式，以及relative和sticky定位</li>
<li>浮动：浮动模式下，一个盒子起初定位在文档流中，然后被从文档流中拿出向左或向右移动。内容会包围在浮动元素的边上</li>
<li>绝对定位：在绝对定位模式下，一个盒子会从文档流中完全脱离，并根据定位所属的包含块进行定位</li>
</ol>
<p>当一个元素时浮动的，或者绝对定位或者是根元素，那么就称它脱离文档流。一个元素没脱离文档流的话就被称为流内元素（in-flow）</p>
<p>&nbsp;</p>
</div>
</div>
</div>
</div>
<p>&nbsp;</p>
<p>参考：[1]http://www.w3.org/TR/2007/WD-css3-box-20070809/&nbsp;</p>
<p>[2]http://www.w3.org/TR/2011/REC-CSS2-20110607/box.html</p>
<p>[3] http://jorux.com/archives/property-4-if-you-love-css/</p>
<p>&nbsp;[4]&nbsp;http://skyinlayer.com/blog/2014/03/31/css-layout/</p></div>