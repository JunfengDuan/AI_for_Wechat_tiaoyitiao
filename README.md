# AI_for_Wechat_tiaoyitiao
人工智能助手 自动微信跳一跳 小游戏  

#### 作者：刘云飞  
 wechat：lyffly  
## 0x00
 支持手机：安卓Android系统 分辨率为1920 * 1080 pix   
 电脑端：windows  
 人工智能版差别在哪：期待AI理解距离的概念，在跳的时候只跳大概距离，不是每次跳中心，非一个精确的数值，这样也可以防止刷分被ban。
 
## 0x01
 首先按照下面进行配置adb和Python环境  
 
[https://github.com/wangshub/wechat_jump_game](https://github.com/wangshub/wechat_jump_game "https://github.com/wangshub/wechat_jump_game")

## 0x02
 安装tensorflow和keras
```shell
pip install tensorflow
pip install keras
```
## 0x03
 下载这里的所有文件

## 0x04
 打开 跳一跳 小游戏  
 在下载后的文件夹内，cmd中运行
```shell
python predict.py
```
即可开始游戏  

效果见视频
[http://www.bilibili.com/video/av17998366](http://www.bilibili.com/video/av17998366 "http://www.bilibili.com/video/av17998366")

截图  
![](https://github.com/lyffly/AI_for_Wechat_tiaoyitiao/blob/master/imgs/demo.png)

## 如果只想刷分，不要再往下看

## 0x05
 备注：本文代码除 深度学习 部分为本人编写  
       其他代码来源于https://github.com/wangshub/wechat_jump_game  

 训练使用的图片已经共享：  
 链接：https://pan.baidu.com/s/1mhCz1Bq 密码：lih7


## 0x06
  知识背景：深度学习，CNN  
  训练图片共3502张，准确率约95%，训练显卡（1050ti），时长约10小时。  

网络结构如下
```shell
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_1 (Conv2D)            (None, 135, 240, 16)      448       
_________________________________________________________________
max_pooling2d_1 (MaxPooling2 (None, 67, 120, 16)       0         
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 67, 120, 32)       4640      
_________________________________________________________________
max_pooling2d_2 (MaxPooling2 (None, 33, 60, 32)        0         
_________________________________________________________________
conv2d_3 (Conv2D)            (None, 33, 60, 64)        18496     
_________________________________________________________________
max_pooling2d_3 (MaxPooling2 (None, 16, 30, 64)        0         
_________________________________________________________________
conv2d_4 (Conv2D)            (None, 16, 30, 64)        36928     
_________________________________________________________________
max_pooling2d_4 (MaxPooling2 (None, 8, 15, 64)         0         
_________________________________________________________________
conv2d_5 (Conv2D)            (None, 8, 15, 128)        73856     
_________________________________________________________________
max_pooling2d_5 (MaxPooling2 (None, 4, 7, 128)         0         
_________________________________________________________________
flatten_1 (Flatten)          (None, 3584)              0         
_________________________________________________________________
dropout_1 (Dropout)          (None, 3584)              0         
_________________________________________________________________
dense_1 (Dense)              (None, 128)               458880    
_________________________________________________________________
dropout_2 (Dropout)          (None, 128)               0         
_________________________________________________________________
dense_2 (Dense)              (None, 27)                3483      
=================================================================
Total params: 596,731
Trainable params: 596,731
Non-trainable params: 0
_________________________________________________________________
Found 3502 images belonging to 27 classes.
```

持续更新中

