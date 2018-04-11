# 该工具的功能为：图像的人脸识别

提供一个带有头像的图片，执行工具，则返回一个以json形式的字符串，如下：

[[0, 2, 786, 999]]

json 解析后，其实是个二维数组，数组的个数即为头像个数，每个子数组代表一个头像的坐标：

左上角坐标为 （0， 2），右下角坐标为 （786， 999）
这个坐标所确定的矩形即为图像中的人脸区域



工具的使用方式

linux系统下，编译之后，把文件 facedetect、haarcascade_frontalface_default.xml 放到任何位置即可（确保这两个文件在同一个目录中），如： /tmp/

然后执行命令 $  /tmp/facedetect  ./sam.jpg  (指向图片的位置)


查看帮助：$  /tmp/facedetect -h

usage: facedetect [-h] [-sf scaleFactor] [-mn minNeighbors] image

positional arguments:
  image             指向图片的路径

optional arguments:
  -h, --help        show this help message and exit
  -sf scaleFactor   specifying how much the image size is reduced at each
                    image scale. 此值的取值范围 1 - 9 默认为1， 当对头像识别不准确时，可适当调节此值
  -mn minNeighbors  specifying how many neighbors each candidate rectangle
                    should have to retain it. 默认值为 5 一般不用设置