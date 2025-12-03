# 一、项目介绍
![](https://fastly.jsdelivr.net/gh/bucketio/img9@main/2025/11/29/1764405013841-06511dcc-2c2e-4002-af3d-99ab5bc4b511.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/29/1764405145864-2d1211d0-3f57-49db-ac39-0dbd636f7fd7.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/11/30/1764459416057-441862c1-08ec-470e-8325-4dff7e3879d7.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764459502291-4da1489c-1c6b-4b41-90a6-d7acdb84f523.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/30/1764515504610-41bf3a8c-d275-429d-8c79-81fcbf3688cc.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764515976670-eeb80ccc-92f5-409a-81f8-eed2ed1a6599.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img8@main/2025/11/30/1764516094591-261df6ac-30a0-4f7e-a364-9c89c6d8a2a9.png)

| 模块分类 | 硬件名称 | 型号/规格 | 数量 | 预估价格 (元) | 作用 |
| :--- | :--- | :--- | :--: | :--: | :--- |
| 主控 | 树莓派 | Raspberry Pi 5 (4GB) | 1 | 420 | 运行 OS、OpenCV 及 PaddleLite 推理核心 |
| 视觉 | 单目相机 | HBVCAM-V2101 V11 | 1 | 30 | 广角图像采集，覆盖桌面学习区域 |
| 运动 | 舵机 | LFD-01 防堵转舵机 + 金属盘 | 2 | 80 | 控制头部/身体转动，模拟“注视”与“摇头”动作 |
| 驱动 | 轮组 | 麦克纳姆轮 (65\*30mm) | 1组 | 120 | 配合 TT 马达实现全向移动，增强交互灵动性 |
| 动力 | 电机 | 塑料轴 TT 马达 | 4 | 80 | 驱动轮组 |
| 交互 | 语音模块 | WonderEchoPro | 1 | 50 | 实现本地语音唤醒与 TTS 语音播报 |
| 感知 | 超声波 | RUS-04 (RGB发光) | 1 | 25 | 距离检测与 RGB 氛围灯效显示 |
| 循迹 | 传感器 | 四路巡线传感器 | 1 | 20 | 辅助定位与防跌落 |
| 电源 | 电池 | 18650 锂电池组 | 2节 | 25 | 系统独立供电 |
| 辅材 | 线材等 | 杜邦线、螺丝、亚克力板 | - | 50 | 结构组装 |
| 总计 | | | | **约 900 元** | |

![](https://fastly.jsdelivr.net/gh/bucketio/img7@main/2025/11/30/1764516287768-96535191-7138-41e7-b9b8-c32bdf94fa1d.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img16@main/2025/12/02/1764683998041-f56ed3f3-a0b3-4141-9d03-117480ea5524.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img17@main/2025/12/02/1764684441740-16570a4c-f503-43ee-94fa-27f9d7d85f36.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764516424933-5f9ef4fe-3c0c-4838-af12-8780038599bd.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/11/30/1764516522950-2956e292-d17a-44e1-9e50-605866c9dffc.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/30/1764516557824-6458fc35-d18c-4465-9a63-08827747182a.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/12/02/1764684738894-185ea126-41b4-40b7-864c-3f48d38605b1.png)

# 二、环境配置

## 2.1 软件

需要安装node和

## 2.2 硬件

### 2.2.1 树莓派ap配网

### 2.2.2 树莓派安装pandle lite

下载inference_lite_lib.armlinux.armv8.gcc.with_extra.with_cv包至树莓派。

# 三、相关代码

硬件代码都存放在work---ella_hardware文件夹下

## 3.1  人物追踪

### 3.1.1 目录说明

```

ella_hardware/
├── 01_person_search_node/      # 人物追踪与搜索节点模块
│   ├── ros2/             # 基于 ROS2 的实现
│   └── no_ros2/           # 使用 Python 的独立实现（无需 ROS2）
└── ros_robot_controller_sdk.py # 控制 SDK

```

### 3.1.2 功能描述

当用户不在“视线”范围内，设备通过旋转车轮和镜头旋转的方式捕捉人物。


### 3.1.3 常见问题（长期更新）

**Q**: 可以改变检测间隔吗？

**A**: 可以！修改 `interval_minutes` 参数：

```python
interval_minutes = 1  # 每1分钟检测一次
interval_minutes = 10  # 每10分钟检测一次
```



## 3.2 端侧部署姿势识别小模型

### 1.下载模型

下载models文件夹内ella_model_v1.nb模型至树莓派。

### 2.模型调用


``` cpp


```


## 3.3 PP-TTS语音合成

### 3.3.1 训练

### 3.3.2 树莓派推理代码

## 3.4 前端项目代码

存放在work---ella_software文件夹下

### 3.4.1 目录说明


### 3.4.2 功能描述


### 3.4.3 常见问题


## 3.5 后端接口代码



# 四、相关演示

# 五、其他

## 5.1 github开源地址

https://github.com/Luchen-0420/Ella-AIPet.git

## 5.2 作者及联系方式
![](https://fastly.jsdelivr.net/gh/bucketio/img11@main/2025/12/02/1764678441795-2c7fa404-cffd-4056-a111-8d05522514c9.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img16@main/2025/12/02/1764674721228-641c1059-bd3c-4118-ae03-4a6f298007c0.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img12@main/2025/12/02/1764675383183-8b060744-2652-413e-9a80-4b46424510ec.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/12/02/1764675871365-37210279-f12d-45d5-ae41-6811a2d81005.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img14@main/2025/12/02/1764675659866-366862e6-3e50-42e0-93df-5d16b0b88281.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img13@main/2025/12/02/1764676558154-a35bda17-816a-411f-b0d8-a15597cfc434.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/12/02/1764676378808-6a5b2f97-f421-4f00-b54c-7f2fa28cce78.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/12/02/1764676913216-931567c5-acc9-4fee-b619-8ee44e47c5d9.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img6@main/2025/12/02/1764677820085-88555d46-f0d1-44cc-84c1-29c7691efc64.png)
