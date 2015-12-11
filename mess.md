# 学习积累
### 平时学到的一些知识暂时记录下来，之后整理。

- ### meta标签
		<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
width - viewport的宽度
height - viewport的高度
initial-scale - 初始的缩放比例
user-scalable - 用户是否可以手动缩放
minimum-scale - 允许用户缩放到的最小比例
maximum-scale - 允许用户缩放到的最大比例

- ### js绑定onclick事件：
注意是**onclick**不是**onClick**。
		var link = document.getElementsByTagName('a');
		for(var i = 0;i<link.length;i++){
			link[i].onclick = function(){
				function XXX();
			}
		}
或者在标签中，如
		
		<a href = "##" onclick = "functionName()"></a>
又或者使用W3C dom中的addEventListener()方法，如

		node.addEventListener("click", functionName, captureFlag);
方法的第一个参数是声明事件类型的字符串（不带"on"前缀），比如click，mousedown，和keypress。
第二个参数是函数引用，**不能加括号**。
第三个参数是一个 Boolean 值，指明该结点是否以DOM中的捕捉模式来侦听事件。对于一个典型的事件侦听器来说，第三个参数应该为false（假）。
IE中只能用attachEvent即node.attachEvent(type, listener); 
node： dom节点 。
type： 字符串，事件名称，含“on”，比如“onclick”、“onmouseover”、“onkeydown”等。 
listener ：实现了 EventListener 接口或者是 JavaScript 中的函数。
- ### rem
相对于根元素的字体大小,css中为html设置

		html{font-size:10px;}
即1rem = 10px
- ### focus事件和blur事件

		link[i].onfocus = function(){
				function XXX();
			}
		link[i].blur = function(){
				function XXX();
			}
- ### window.onload
window.onload是在dom文档树和所有文件加载完之后执行一个函数。

- ### json2html jquery实现

		var json ={
    	"title":"xxx",
    	"context":"demodemodemo",
    	"author":"ringotc" 
		}

		$('<div class="post"> <h1>'+json.title+'</h1> <div class="context">'+json.context+'</div> <p>'+json.author+'</p> </div>').append('body')
- ### 清除浮动
父级元素后加

		a:after {
			display: block;
			clear: both;
			width: 0;
			height: 0;
			visibility: hidden;
			overflow: hidden;
			content: " ";
		}

- ### 溢出滚动
CSS中"overflow:scroll"默认是左右，上下都滚动
如果左右没有超出内容时，用overflow:auto;
如果左右有超出内容，用overflow-x: hidden;