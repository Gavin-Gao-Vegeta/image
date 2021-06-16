1图片裁剪

　　获取裁剪框（矩形）相对于画布的位置（左上）和裁剪框的height、width。获取（getImageData）canvas相应位置的图片对象（ImageData）。清空canvas画布。在canvas画布的相应位置绘制（putImageData）获取的图片对象（ImageData）。生成预览图。

2图片马赛克

　　马赛克的绘制，就是在以鼠标划过路径（画笔宽度）为中心的区域，重新绘制成其他的颜色。一般结果是，会取周围的相近的颜色。

　　取色方法：

　　1）比如现有一鼠标划过的点的坐标（x,y），定义一个矩形左上角坐标取（x,y），宽30px，高30px。我们把矩形宽高都除以5（分成5份，可以自定义为n份），所以现在是25个6px的小格子。每个小格子宽高都是6px。

　　2）然后，我们随机获取一个小格子，获取（getImageData）这个小格子的图片对象（ImageData）；再随机获取此图片对象上某个像素点（宽1px，高1px）的颜色color（rgba：ImageData.data[0]，ImageData.data[1]，ImageData.data[2]，ImageData.data[3]）；最后我们把第一个6x6px的小格子的每个像素点的颜色都设置为color。

　　3）其他24个小格子的颜色，遍历2步骤即可。# image
