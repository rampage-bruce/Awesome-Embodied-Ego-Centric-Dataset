# Nymeria 数据集家族

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 / 2026 |
| 机构 | Meta Reality Labs Research; University of Tuebingen; Max Planck Institute for Informatics; Stanford University; Nanyang Technological University |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [Nymeria: A Massive Collection of Multimodal Egocentric Daily Motion in the Wild](https://arxiv.org/abs/2406.09905); [NymeriaPlus: Enriching Nymeria Dataset with Additional Annotations and Data](https://arxiv.org/abs/2603.18496) |
| 项目 / 数据 | https://www.projectaria.com/datasets/nymeria/; https://explorer.projectaria.com/nymeria; https://explorer.projectaria.com/nymeriaplus |
| 代码 | https://github.com/facebookresearch/nymeria_dataset |

## 版本

### Nymeria

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 已发布数据 | 去标识化 Aria / 腕带记录、IMU、眼动、设备轨迹、点云 / 地图与 XSens 动作 |
| 监督信号 | 全身 / 手腕运动、设备轨迹、眼动、场景几何、动作旁白、原子动作与活动摘要 |
| 规模 | 300 小时；当前发布 1,100 个序列；264 名参与者；50 个地点 |

### NymeriaPlus

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 已发布数据 | Nymeria 采集数据，以及底图、腕带视频、头显音频、优化人体动作与物体几何 |
| 监督信号 | 稠密 3D / 可见 2D 物体框；实例级物体重建网格；更新后人体动作 |
| 规模 | 基于同一批采集数据；当前发布 1,100 个序列 |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 人手 |
| 采集条件 | 自然环境 |
| 场景 | 家庭、办公室、校园、室内与户外 |
| 采集设备 | Project Aria；2 个 miniAria 腕带；XSens MVN Link 动捕服；观察者 Project Aria |
| 相机设置 | 人类第一视角：头戴式；另有腕载相机与移动观察相机 |
| 实际采集数据 | 头显、双腕带与观察者的 RGB / 灰度 / IMU / 音频 / 眼动；XSens 全身惯性动捕 |
| 已发布数据 | 多相机 RGB / 灰度视频；IMU；眼动；音频；场景 / 物体几何 |

## 监督信号与数据构建

- 身体 / 手腕运动 ← XSens 动捕 + 重定向。
- 设备轨迹 / 场景几何 ← Aria MPS + 光束法平差。
- 语言 ← 人工标注。
- 物体网格 ← ShapeR + 人工筛选。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 300 小时；当前发布 1,100 个序列；264 名参与者；50 个地点；20 类场景 |
| 开放与获取 | 受限访问：数据、标注与工具包（CC BY-NC 4.0）；[官方入口](https://www.projectaria.com/datasets/nymeria/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| π0（EgoScalerV2） | 决策 / 动作 | 预训练 | Nymeria RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | [EgoScalerV2 论文](https://arxiv.org/abs/2509.21986) |
| HMD² | 预测 / 世界建模 | 训练 + 评测 | Project Aria 图像、头部运动与场景点云用于在线生成佩戴者全身运动 | [HMD² 项目页](https://hmdsquared.github.io/)；[论文](https://openreview.net/pdf?id=sQe8zAYt5c) |

## 官方来源

- 论文： [Nymeria, ECCV 2024](https://arxiv.org/abs/2406.09905); [NymeriaPlus, 2026](https://arxiv.org/abs/2603.18496)
- 项目页： https://www.projectaria.com/datasets/nymeria/
- 官方仓库： https://github.com/facebookresearch/nymeria_dataset
- 数据页： https://explorer.projectaria.com/nymeria; https://explorer.projectaria.com/nymeriaplus
- 文档： [下载与查看工具](https://github.com/facebookresearch/nymeria_dataset)；[Aria Dataset Explorer](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/dataset_explorer)；[许可证](https://github.com/facebookresearch/nymeria_dataset/blob/main/NYMERIA_DATASET_LICENSE)
