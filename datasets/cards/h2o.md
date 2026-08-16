# H2O

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2021 |
| 机构 | ETH Zurich; Microsoft; Samsung AI Center, Cambridge |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [H2O: Two Hands Manipulating Objects for First Person Interaction Recognition](https://openaccess.thecvf.com/content/ICCV2021/html/Kwon_H2O_Two_Hands_Manipulating_Objects_for_First_Person_Interaction_Recognition_ICCV_2021_paper.html) |
| 项目 / 数据 | https://taeinkwon.com/projects/h2o/; https://h2odataset.ethz.ch/; [ETH Research Collection](https://doi.org/10.3929/ethz-b-000685070) |
| 代码 | https://github.com/taeinkwon/h2odataset |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 受控真实环境 |
| 场景 | 大厅、办公室与厨房 |
| 采集设备 | 5 台硬件同步的 Microsoft Azure Kinect DK |
| 相机设置 | 人类第一视角：1 台头戴式 RGB-D 相机、移动；第三视角：4 台固定 RGB-D 相机 |
| 实际采集数据 | 1 路第一视角 + 4 路第三视角同步 RGB-D；反光标定球深度观测；独立物体扫描 |
| 已发布数据 | 五视角 RGB-D；点云；物体网格 |

## 监督信号与数据构建

- 手部位姿 ← OpenPose + 多视角 RGB-D MANO 优化 + 人工质检。
- 相机位姿 ← 标定 + 卡尔曼滤波。
- 物体位姿 ← Mask R-CNN + DenseFusion + ICP。
- 动作 ← 人工标注。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 571,645 个五视角 RGB-D 帧；4 名参与者；36 个动作类别 |
| 开放与获取 | 公开：数据、标注、下载工具与查看工具（CC BY-NC 4.0）；[官方入口](https://doi.org/10.3929/ethz-b-000685070) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 使用原生 RGB-D、双手 / 相机标注；EgoSmith 补充语言并统一格式；保留 1.0 小时 / 935 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| USST | 预测 / 世界建模 | 训练 + 评测 | 第一视角 RGB 与历史手部运动用于预测未来 2D / 3D 手部轨迹 | [USST 论文](https://arxiv.org/abs/2307.08243) |

## 官方来源

- 论文： [ICCV 2021](https://openaccess.thecvf.com/content/ICCV2021/html/Kwon_H2O_Two_Hands_Manipulating_Objects_for_First_Person_Interaction_Recognition_ICCV_2021_paper.html)；[arXiv](https://arxiv.org/abs/2104.11181)
- 项目页： https://taeinkwon.com/projects/h2o/
- 官方仓库： https://github.com/taeinkwon/h2odataset; [H2OPlayer](https://github.com/taeinkwon/h2oplayer)
- 数据页： https://h2odataset.ethz.ch/; [ETH Research Collection / DOI](https://doi.org/10.3929/ethz-b-000685070)
- 文档： [dataset structure and labels](https://github.com/taeinkwon/h2odataset#dataset-structure); [registration terms](https://h2odataset.ethz.ch/)
