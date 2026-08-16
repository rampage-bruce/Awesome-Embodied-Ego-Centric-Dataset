# EgoPAT3D 数据集家族

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2022 / 2024 |
| 机构 | New York University；Tongji University；Tsinghua University（初始版本）；EgoPAT3Dv2 另有 North Carolina State University；EgoPAT3D-DT / USST 由 Michigan State University、OPPO US Research Center、Texas A&M University 与 University at Buffalo 发布 |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [Egocentric Prediction of Action Target in 3D](https://openaccess.thecvf.com/content/CVPR2022/html/Li_Egocentric_Prediction_of_Action_Target_in_3D_CVPR_2022_paper.html); [Uncertainty-aware State Space Transformer for Egocentric 3D Hand Trajectory Forecasting](https://openaccess.thecvf.com/content/ICCV2023/html/Bao_Uncertainty-aware_State_Space_Transformer_for_Egocentric_3D_Hand_Trajectory_Forecasting_ICCV_2023_paper.html); [EgoPAT3Dv2: Predicting 3D Action Target from 2D Egocentric Vision for Human-Robot Interaction](https://arxiv.org/abs/2403.05046) |
| 项目 / 数据 | [EgoPAT3D](https://ai4ce.github.io/EgoPAT3D/)；[EgoPAT3Dv2](https://ai4ce.github.io/EgoPAT3Dv2/)；[EgoPAT3D 下载页](https://ai4ce.github.io/EgoPAT3D/portfolio.html)；[EgoPAT3Dv2 数据页](https://huggingface.co/datasets/ai4ce/EgoPAT3Dv2) |
| 代码 | https://github.com/ai4ce/EgoPAT3D; https://github.com/ai4ce/EgoPAT3Dv2; https://github.com/oppo-us-research/USST |

## 版本

### EgoPAT3D 1.0

| 字段 | 内容 |
| --- | --- |
| 年份 | 2022 |
| 已发布数据 | Azure Kinect MKV：RGB、深度、红外、IMU、温度；抽取 RGB；15 个场景点云 |
| 监督信号 | 手部存在、MediaPipe 手部关键点、相机变换、2D / 3D 动作目标、动作片段边界 |
| 规模 | 10 小时；150 段记录；15,000 次手物动作；2 名参与者 |

### EgoPAT3D-DT

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 已发布数据 | 从 EgoPAT3D 1.0 提取的 RGB 片段 |
| 监督信号 | 逐帧 2D、局部 3D 与全局 3D 手部轨迹 |
| 规模 | 11,141 个轨迹样本 |

### EgoPAT3Dv2

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 已发布数据 | 原始 MKV、RGB、对齐深度、点云、变换矩阵与 HDF5 标注 |
| 监督信号 | 人工核验手部关键点、扩展 2D / 3D 动作目标与相机变换 |
| 规模 | 9,579 个片段；扩展家族共 11 名参与者 |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 单手 |
| 采集条件 | 受控真实环境 |
| 场景 | 厨房、卧室与浴室 |
| 采集设备 | 头盔安装的 Microsoft Azure Kinect DK；KinectFusion / KinFu 场景扫描 |
| 相机设置 | 人类第一视角：头戴 / 头盔式、移动、RGB-D |
| 实际采集数据 | Azure Kinect 同步 RGB、深度、红外、IMU 与温度；每个原始场景另采集静态点云 |
| 已发布数据 | 单目 RGB-D；IMU；红外；温度；场景点云 |

## 监督信号与数据构建

- 手部关键点 ← MediaPipe + v2 人工核验。
- 稠密轨迹 ← 关键点 + RAFT + 深度 + RGB-D 里程计。
- 相机运动 ← ICP / RGB-D 里程计。
- 动作目标 ← 人工片段边界 + 手部 / 深度几何。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | v1：10 小时、150 段记录、15K 个动作；v2：9,579 个片段、11 名参与者；DT：11,141 个样本；动作类型包括到达、抓取、移动与放置 |
| 开放与获取 | 公开：数据、标注与代码；[官方入口](https://ai4ce.github.io/EgoPAT3D/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoPAT3D LSTM baseline | 预测 / 世界建模 | 训练 + 评测 | RGB-D、IMU、历史手部位置与视觉里程计用于连续预测 3D 操作目标 | [EgoPAT3D 项目页](https://ai4ce.github.io/EgoPAT3D/about.html)；[论文](https://openaccess.thecvf.com/content/CVPR2022/html/Li_Egocentric_Prediction_of_Action_Target_in_3D_CVPR_2022_paper.html) |
| USST | 预测 / 世界建模 | 训练 + 评测 | 第一视角 RGB 与历史手部运动用于预测未来 2D / 3D 手部轨迹 | [USST 论文](https://arxiv.org/abs/2307.08243) |
| EgoPAT3Dv2 baseline | 预测 / 世界建模 | 训练 + 评测 | RGB 与 MediaPipe 手部关键点用于预测 3D 操作目标，并在真实协作机器人任务中验证 | [EgoPAT3Dv2 论文与项目页](https://ai4ce.github.io/EgoPAT3Dv2/) |

## 官方来源

- 论文： [EgoPAT3D, CVPR 2022](https://openaccess.thecvf.com/content/CVPR2022/html/Li_Egocentric_Prediction_of_Action_Target_in_3D_CVPR_2022_paper.html); [USST, ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/html/Bao_Uncertainty-aware_State_Space_Transformer_for_Egocentric_3D_Hand_Trajectory_Forecasting_ICCV_2023_paper.html); [EgoPAT3Dv2, ICRA 2024](https://arxiv.org/abs/2403.05046)
- 项目页： [EgoPAT3D](https://ai4ce.github.io/EgoPAT3D/)；[EgoPAT3Dv2](https://ai4ce.github.io/EgoPAT3Dv2/)
- 官方仓库： https://github.com/ai4ce/EgoPAT3D; https://github.com/ai4ce/EgoPAT3Dv2; https://github.com/oppo-us-research/USST
- 数据页： [EgoPAT3D](https://ai4ce.github.io/EgoPAT3D/portfolio.html)；[EgoPAT3Dv2](https://huggingface.co/datasets/ai4ce/EgoPAT3Dv2)；[EgoPAT3D-DT / USST](https://github.com/oppo-us-research/USST)
- 文档： [EgoPAT3D 发布结构与真值生成](https://github.com/ai4ce/EgoPAT3D)；[EgoPAT3Dv2 数据卡](https://huggingface.co/datasets/ai4ce/EgoPAT3Dv2)；[USST 标注补充材料](https://openaccess.thecvf.com/content/ICCV2023/supplemental/Bao_Uncertainty-aware_State_Space_ICCV_2023_supplemental.pdf)
