请到官网下载或者点击[百度网盘链接](https://pan.baidu.com/s/1X-ZWCvT8Y1l_qJH-B9aIvQ )，密码：yolo

## 预训练检查点

| 模型                                                         | 尺寸 （像素） | 地图VAL 0.5：0.95 | 地图VAL 0.5   | 速度 CPU b1 (ms) | 速度 V100 b1 (ms) | 速度 V100 b32 (ms) | 参数 (M) | FLOPs [@640](https://github.com/640) (B) |
| ------------------------------------------------------------ | ------------- | ----------------- | ------------- | ---------------- | ----------------- | ------------------ | -------- | ---------------------------------------- |
| [YOLOv5n](https://github.com/ultralytics/yolov5/releases)    | 640           | 28.4              | 46.0          | **45**           | **6.3**           | **0.6**            | **1.9**  | **4.5**                                  |
| [YOLOv5s](https://github.com/ultralytics/yolov5/releases)    | 640           | 37.2              | 56.0          | 98               | 6.4               | 0.9                | 7.2      | 16.5                                     |
| [YOLOv5m](https://github.com/ultralytics/yolov5/releases)    | 640           | 45.2              | 63.9          | 224              | 8.2               | 1.7                | 21.2     | 49.0                                     |
| [YOLOv5l](https://github.com/ultralytics/yolov5/releases)    | 640           | 48.8              | 67.2          | 430              | 10.1              | 2.7                | 46.5     | 109.1                                    |
| [YOLOv5x](https://github.com/ultralytics/yolov5/releases)    | 640           | 50.7              | 68.9          | 766              | 12.1              | 4.8                | 86.7     | 205.7                                    |
|                                                              |               |                   |               |                  |                   |                    |          |                                          |
| [YOLOv5n6](https://github.com/ultralytics/yolov5/releases)   | 1280          | 34.0              | 50.7          | 153              | 8.1               | 2.1                | 3.2      | 4.6                                      |
| [YOLOv5s6](https://github.com/ultralytics/yolov5/releases)   | 1280          | 44.5              | 63.0          | 385              | 8.2               | 3.6                | 16.8     | 12.6                                     |
| [YOLOv5m6](https://github.com/ultralytics/yolov5/releases)   | 1280          | 51.0              | 69.0          | 887              | 11.1              | 6.8                | 35.7     | 50.0                                     |
| [YOLOv5l6](https://github.com/ultralytics/yolov5/releases)   | 1280          | 53.6              | 71.6          | 1784             | 15.8              | 10.5               | 76.8     | 111.4                                    |
| [YOLOv5x6](https://github.com/ultralytics/yolov5/releases) + [TTA](https://github.com/ultralytics/yolov5/issues/303) | 1280 1536     | 54.7 **55.4**     | **72.4** 72.3 | 3136 -           | 26.2 -            | 19.4 -             | 140.7 -  | 209.8 -                                  |

* 所有检查点都使用默认设置训练到 300 个epochs。Nano 模型使用[hyp.scratch-low.yaml](https://github.com/ultralytics/yolov5/blob/master/data/hyps/hyp.scratch-low.yaml)超参数，所有其他模型使用[hyp.scratch-high.yaml](https://github.com/ultralytics/yolov5/blob/master/data/hyps/hyp.scratch-high.yaml)。
* **mAP val**值适用于[COCO val2017](http://cocodataset.org/)数据集上的单模型单尺度。
  转载`python val.py --data coco.yaml --img 640 --conf 0.001 --iou 0.65`
* **速度**平均超过使用[AWS p3.2xlarge](https://aws.amazon.com/ec2/instance-types/p3/)实例 COCO VAL图像。不包括 NMS 时间 (~1 ms/img)。
  Reproduce : `python val.py --data coco.yaml --img 640 --conf 0.25 --iou 0.45`
* **TTA** [测试时间增强](https://github.com/ultralytics/yolov5/issues/303)(包括反射和规模增强)。
  Reproduce :`python val.py --data coco.yaml --img 1536 --iou 0.7 --augment`

