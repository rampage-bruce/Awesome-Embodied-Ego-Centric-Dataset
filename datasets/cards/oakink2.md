# OakInk2

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 机构 | Shanghai Jiao Tong University; South China University of Technology |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [OAKINK2: A Dataset of Bimanual Hands-Object Manipulation in Complex Task Completion](https://openaccess.thecvf.com/content/CVPR2024/html/Zhan_OAKINK2_A_Dataset_of_Bimanual_Hands-Object_Manipulation_in_Complex_Task_CVPR_2024_paper.html) |
| 项目 / 数据 | [项目与下载](https://oakink.net/v2) |
| 代码 | [官方工具包](https://github.com/oakink/OakInk2)；[TaMF 基线](https://github.com/oakink/OakInk2-TaMF) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 实验室 |
| 场景 | 复杂日常任务 |
| 采集设备 | 4 台通用 RGB 相机；12 台 OptiTrack Prime 13W 红外动捕相机 |
| 相机设置 | 人类第一视角：1 台佩戴式 RGB 相机、移动；第三视角：3 台固定 RGB 相机 |
| 实际采集数据 | 4 路同步 RGB；身体、手与物体的光学标记轨迹 |
| 已发布数据 | 多视角 RGB；物体模型 |

## 监督信号与数据构建

- 身体 / 手部位姿 ← 动捕 + 参数化模型拟合。
- 物体位姿 ← 动捕 + 几何。
- 任务目标、操作基元与执行路径 ← 官方程序标注。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 627 个序列；401 万张图像；9 名参与者 |
| 开放与获取 | 预览发布：数据、标注与工具包；[官方入口](https://oakink.net/v2) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| TaMF / Complex Task Completion | 预测 / 世界建模 | 训练 + 评测 | 原子 / 复杂任务层级、物体轨迹与双手运动 | [论文](https://openaccess.thecvf.com/content/CVPR2024/html/Zhan_OAKINK2_A_Dataset_of_Bimanual_Hands-Object_Manipulation_in_Complex_Task_CVPR_2024_paper.html)；[TaMF 代码](https://github.com/oakink/OakInk2-TaMF) |
| EgoSteer | 决策 / 动作 | 预训练 | EgoSmith 从 OakInk2 保留 1.7 小时 / 891 个片段，并生成深度监督 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |

## 官方来源

- 论文：[CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Zhan_OAKINK2_A_Dataset_of_Bimanual_Hands-Object_Manipulation_in_Complex_Task_CVPR_2024_paper.html)
- 项目与数据页：[OakInk2](https://oakink.net/v2)
- 工具包与格式文档：[官方仓库](https://github.com/oakink/OakInk2)
- 基线代码：[TaMF](https://github.com/oakink/OakInk2-TaMF)
- 使用论文：[EgoSteer](https://arxiv.org/abs/2607.09701)
