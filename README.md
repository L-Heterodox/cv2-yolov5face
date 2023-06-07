# cv2-yolov5face
1.搭建pytorch对应环境并git clone官方开源代码\
2.下载数据集和标签，转化为yolo数据格式，并正确组织数据集结构，修改代码中传入路径,下面会给出本次实验已经转换好的数据（百度网盘链接），可直接用于训练\
3.在服务器上使用widerface训练集训练模型，记录训练过程并保存效果最好的模型权重和最后一个模型权重（RTX A5000训练了一个晚上）\
4.加载效果最好的模型权重，对widerface验证集进行检测，生成文本文件\
5.对比验证集真值，得出该模型在验证集的测试效果\
6.输入单张照片进行测试，可视化实验结果

文件夹组织架构：\
├─data\
│  ├─images\
│  ├─scripts\
│  └─widerface：本实验需要的原始数据集、标签及转化后数据，下面将给出百度网盘链接\
│      ├─images\
│      │  ├─0--Parade\
        ...\
│      │  ├─61--Street_Battle\
│      ├─train\
│      │  ├─images\
│      │  └─labels\
│      └─val\
│          ├─images\
│          └─labels\
├─del\
├─models\
│  └─__pycache__\
├─runs\
│  ├─detect\
│  │  ├─exp\
   ...\
│  └─train：训练过程产生的结果放置在对应文件夹\
│      ├─exp\
│      │  └─weights\
      ...
├─torch2trt\
│  └─imgs\
├─utils\
│  ├─aws\
│  ├─google_app_engine\
│  ├─wandb_logging\
│  └─__pycache__\
├─weights：包括官方开源的权重和本次实验自己训练的权重（best和last），下面会给出百度网盘链接\
├─widerface_evaluate：在val上评估\
│  ├─build\
│  │  ├─lib.win-amd64-3.9\
│  │  ├─temp.linux-x86_64-3.7\
│  │  ├─temp.linux-x86_64-3.8\
│  │  └─temp.win-amd64-3.9\
│  │      └─Release\
│  ├─ground_truth：真值（可在主页retinaface中找到下载链接）\
│  └─widerface_txt：best模型在val上结果\
└─__pycache__

一些可能用到的百度网盘链接：\
data（包含全部数据集及转化后形式，可直接用于训练）：链接：https://pan.baidu.com/s/1ztLDqOMcX9gXjduucUWJQQ?pwd=i3cv 提取码：i3cv \
weights（包含一些官方开源的预训练权重和本次训练产生的权重best和last）：链接：https://pan.baidu.com/s/1RUs_uXmql4yCd77N87VG7A?pwd=d9sl 提取码：d9sl \
woderface_txt（best模型在val上结果）:链接：https://pan.baidu.com/s/1s4Q97S5eQqn2C_9P0RZQfQ?pwd=bdao 提取码：bdao 

参考链接：\
YOLO5Face: Why Reinventing a Face Detector：https://arxiv.org/abs/2105.12931 \
代码参考：\
https://github.com/deepcam-cn/yolov5-face


