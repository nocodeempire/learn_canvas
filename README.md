# Canvas学习笔记


#### <canvas> 元素
````html
<canvas id="tutorial" width="150" height="150"></canvas>
````
当没有设置宽度和高度的时候，canvas会初始化宽度为300像素和高度为150像素。  
注意: 如果你绘制出来的图像是扭曲的, 尝试用width和height属性为canvas明确规定宽高，而不是使用CSS。  
canvas元素可以像任何一个普通的图像一样（有margin，border，background等等属性）被设计。  
<strong>我们只是在canvas标签中提供了替换内容。不支持canvas的浏览器将会忽略容器并在其中渲染后备内容。而支持的浏览器将会忽略在容器中包含的内容，并且只是正常渲染canvas。</strong>

#### 栅格
<img src="https://mdn.mozillademos.org/files/224/Canvas_default_grid.png" />  

#### 绘制矩形
不同于SVG，HTML中的元素canvas只支持一种原生的图形绘制：矩形。
````html
canvas提供了三种方法绘制矩形：
fillRect(x, y, width, height)
绘制一个填充的矩形
strokeRect(x, y, width, height)
绘制一个矩形的边框
clearRect(x, y, width, height)
清除指定矩形区域，让清除部分完全透明。
````
````js
function draw() {
 var canvas = document.getElementById('canvas'); 
 if (canvas.getContext) { // 判断是否支持canvas
  var ctx = canvas.getContext('2d');  
   ctx.fillRect(25,25,100,100);
   ctx.clearRect(45,45,60,60);
   ctx.strokeRect(50,50,50,50);
 }
}
````
<img src="https://mdn.mozillademos.org/files/245/Canvas_rect.png" />  

#### 绘制路径
````html
图形的基本元素是路径。路径是通过不同颜色和宽度的线段或曲线相连形成的不同形状的点的集合。一个路径，甚至一个子路径，都是闭合的。使用路径绘制图形需要一些额外的步骤。
   1.首先，你需要创建路径起始点。
   2.然后你使用画图命令去画出路径。
   3.之后你把路径封闭。
   4.一旦路径生成，你就能通过描边或填充路径区域来渲染图形。

以下是所要用到的函数：
beginPath()
新建一条路径，生成之后，图形绘制命令被指向到路径上生成路径。
closePath()
闭合路径之后图形绘制命令又重新指向到上下文中。
stroke()
通过线条来绘制图形轮廓。
fill()
通过填充路径的内容区域生成实心的图形。
````
````js
function draw() { // 实心三角形
  var canvas = document.getElementById('canvas');
  if (canvas.getContext){
   var ctx = canvas.getContext('2d');
   ctx.beginPath();
   ctx.moveTo(75,50);
   ctx.lineTo(100,75);
   ctx.lineTo(100,25);
   ctx.fill();
  }
}
````
<img src="https://mdn.mozillademos.org/files/9847/triangle.png" />  


















