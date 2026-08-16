# SHOW3D

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 机构 | Meta Reality Labs; Yale University |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [SHOW3D: Capturing Scenes of 3D Hands and Objects in the Wild](https://openaccess.thecvf.com/content/CVPR2026/papers/Rim_SHOW3D_Capturing_Scenes_of_3D_Hands_and_Objects_in_the_CVPR_2026_paper.pdf) |
| 项目 / 数据 | https://show3d-dataset.github.io/; https://huggingface.co/datasets/facebook/show3d-dataset |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 自然环境 |
| 场景 | 室内外多场景 |
| 采集设备 | 8 相机背负式灰度采集架；Meta Quest 3 双前向相机；5 台采集架动捕相机 |
| 相机设置 | 人类第一视角：2 个头显相机、移动；第三视角：背负式采集架上的 8 个移动相机 |
| 实际采集数据 | 10 路硬件同步灰度鱼眼视频；头显相对采集架的动捕轨迹 |
| 已发布数据 | 十视角灰度视频；相机标定；手部 / 物体位姿；场景描述；物体模型 |

## 监督信号与数据构建

- 手部位姿 ← Sapiens / InterNet + 多视角三角化 + 个性化拟合。
- 物体位姿 ← CNOS + FoundPose + GoTrack。
- 相机位姿 ← 头显动捕。
- 描述文本 ← 采集指令 + LLM 改写扩增。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 20 小时；2,137 段记录；428 万个多视角帧；4,250 万张图像 |
| 开放与获取 | 公开：数据、标注与文档（CC BY-NC 4.0）；[官方入口](https://show3d-dataset.github.io/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| InterField | 具身感知 | 训练 + 评测 | 手部 / 物体网格与视频用于逐顶点手—物距离场估计及跨数据集评测 | [SHOW3D 论文](https://arxiv.org/abs/2603.28760) |
| Text-conditioned 6DoF pose forecasting baseline | 预测 / 世界建模 | 训练 + 评测 | 历史物体位姿与场景描述用于预测 30 / 60 帧后的物体 6DoF 位姿 | [SHOW3D 论文](https://arxiv.org/abs/2603.28760) |

## 官方来源

- 论文： [CVPR 2026](https://openaccess.thecvf.com/content/CVPR2026/papers/Rim_SHOW3D_Capturing_Scenes_of_3D_Hands_and_Objects_in_the_CVPR_2026_paper.pdf)；[arXiv](https://arxiv.org/abs/2603.28760)
- 项目页： https://show3d-dataset.github.io/
- 数据页： https://huggingface.co/datasets/facebook/show3d-dataset
- 文档： [raw scenes/calibration](https://huggingface.co/datasets/facebook/show3d-dataset/blob/main/scenes/README.md); [hand pose](https://huggingface.co/datasets/facebook/show3d-dataset/blob/main/hand_pose/README.md); [object pose](https://huggingface.co/datasets/facebook/show3d-dataset/blob/main/object_pose/README.md); [captions](https://huggingface.co/datasets/facebook/show3d-dataset/blob/main/captions/README.md); [quickstart](https://huggingface.co/datasets/facebook/show3d-dataset/blob/main/quickstart.ipynb)
