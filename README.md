# Ella-AIPet
Ella——基于文心一言4.5的AI监督陪伴桌宠




![](https://fastly.jsdelivr.net/gh/bucketio/img9@main/2025/11/29/1764405013841-06511dcc-2c2e-4002-af3d-99ab5bc4b511.png)

# 一、项目简介
## 1.1 项目背景
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/29/1764405145864-2d1211d0-3f57-49db-ac39-0dbd636f7fd7.png)

## 1.2 场景价值
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/11/30/1764459416057-441862c1-08ec-470e-8325-4dff7e3879d7.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764459502291-4da1489c-1c6b-4b41-90a6-d7acdb84f523.png)

# 二、实现原理与技术架构

## 2.1 系统总体软件架构
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/30/1764515504610-41bf3a8c-d275-429d-8c79-81fcbf3688cc.png)


## 2.2 核心技术栈
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764515976670-eeb80ccc-92f5-409a-81f8-eed2ed1a6599.png)


# 三、硬件方案说明

## 3.1 核心硬件清单与成本
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

## 3.2 树莓派扩展板电路设计
![](https://fastly.jsdelivr.net/gh/bucketio/img7@main/2025/11/30/1764516287768-96535191-7138-41e7-b9b8-c32bdf94fa1d.png)


# 四、核心创新点：One-Shot 全合成数据管线
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/30/1764516324157-9a3ff9b5-3a43-493c-b298-70ae947d11c4.png)


# 五、软件接口设计与通信协议
![](https://fastly.jsdelivr.net/gh/bucketio/img13@main/2025/11/30/1764516367358-80ec8c1d-352b-4759-ad95-e6a41ac0b4aa.png)

# 六、应用场景与市场分析
![](https://fastly.jsdelivr.net/gh/bucketio/img15@main/2025/11/30/1764516424933-5f9ef4fe-3c0c-4838-af12-8780038599bd.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2025/11/30/1764516522950-2956e292-d17a-44e1-9e50-605866c9dffc.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img18@main/2025/11/30/1764516557824-6458fc35-d18c-4465-9a63-08827747182a.png)
![](https://fastly.jsdelivr.net/gh/bucketio/img8@main/2025/11/30/1764516614497-89327e03-4975-43db-8c8e-5b596c00a7b7.png)

# 八、相关代码
