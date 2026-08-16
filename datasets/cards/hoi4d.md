# HOI4D

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2022 |
| 机构 | Tsinghua University; Peking University; Shanghai Qi Zhi Institute |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [HOI4D: A 4D Egocentric Dataset for Category-Level Human-Object Interaction](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_HOI4D_A_4D_Egocentric_Dataset_for_Category-Level_Human-Object_Interaction_CVPR_2022_paper.html) |
| 项目 / 数据 | [项目页](https://hoi4d.github.io/)；[数据下载](https://hoi4d.github.io/#data-resources) |
| 代码 | https://github.com/leolyliu/HOI4D-Instructions |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 单手 |
| 采集条件 | 受控真实环境 |
| 场景 | 室内家居、桌面与家具交互 |
| 采集设备 | 自行车头盔采集架；Kinect v2 与 Intel RealSense D455 RGB-D 相机 |
| 相机设置 | 人类第一视角：头戴式、移动、RGB-D |
| 实际采集数据 | Kinect v2 与 RealSense D455 两路同步头戴 RGB-D；另行采集物体彩色照片用于网格重建 |
| 已发布数据 | 对齐 RGB-D；点云 |

## 监督信号与数据构建

- 手部位姿 ← 稀疏人工关键点 + MANO 优化 / 人工修正。
- 相机位姿 ← RGB-D SLAM。
- 物体位姿 ← 人工锚点 + RGB-D 优化。
- 分割 / 动作 ← 人工标注 + 传播 / 重建。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 4,000 个序列；240 万个传感器帧；54 项任务 |
| 开放与获取 | 部分公开：数据、标注与代码（CC BY-NC 4.0）；[官方入口](https://hoi4d.github.io/#data-resources) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| P4Transformer baseline | 具身感知 | 训练 + 评测 | 4D 点云与逐点语义标签用于时空点云语义分割 | [HOI4D 论文](https://arxiv.org/abs/2203.01577) |
| GAIL dexterous-manipulation baseline | 决策 / 动作 | 训练 + 评测 | 人手与物体位姿经重定向生成 12 条 Adroit Hand 状态—动作示范，用于灵巧手拾取策略学习 | [HOI4D 论文附录 D](https://arxiv.org/html/2203.01577#Sx12) |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 2,966 个片段经筛选和手部重建，得到 7.2 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- 论文： [CVPR 2022](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_HOI4D_A_4D_Egocentric_Dataset_for_Category-Level_Human-Object_Interaction_CVPR_2022_paper.html)；[补充材料](https://hoi4d.github.io/supp_cvpr2022.pdf)；[arXiv](https://arxiv.org/abs/2203.01577)
- 项目页： https://hoi4d.github.io/
- 官方仓库： https://github.com/leolyliu/HOI4D-Instructions
- 数据页： [数据与资源](https://hoi4d.github.io/#data-resources)
- 文档： [使用说明](https://github.com/leolyliu/HOI4D-Instructions#readme)；[发布清单](https://github.com/leolyliu/HOI4D-Instructions/blob/main/release.txt)；[测试清单](https://github.com/leolyliu/HOI4D-Instructions/blob/main/testset.txt)；[任务定义](https://github.com/leolyliu/HOI4D-Instructions/blob/main/definitions/task/task_definitions.csv)
