# EgoScalerV2

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Kyoto University; National Institute of Informatics; Institute of Science Tokyo; Sony Interactive Entertainment; NII LLMC |
| 数据角色 | 机器人对齐的人类数据 |
| 论文 | [Developing Vision-Language-Action Model from Egocentric Videos](https://arxiv.org/abs/2509.21986) |
| 项目 / 数据 | [项目页](https://biscue5.github.io/egovla-project-page/)；[数据集](https://huggingface.co/datasets/Biscue5/egoscaler-v2) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 取决于聚合源数据 |
| 场景 | Ego4D、Ego-Exo4D、HD-EPIC 与 Nymeria 日常活动 |
| 采集设备 | 沿用 Ego4D、Ego-Exo4D、HD-EPIC 与 Nymeria 的采集设备 |
| 相机设置 | 人类第一视角取决于源数据，主要为头戴移动视角 |
| 实际采集数据 | 源数据 RGB；几何、物体状态与动作由 EgoScaler 流程重建 |
| 已发布数据 | 224 × 224 RGB；6DoF 物体状态 / 动作；任务文本（LeRobot v2） |

## 监督信号与数据构建

- 任务 / 物体 / 交互区间 ← GPT-4o。
- 物体状态 ← 分割 + 稠密 3D 跟踪 + 配准 / SVD。
- 动作 ← 相邻物体位姿差分。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 45,157 个片段；1,409,418 帧；30,214 条任务文本 |
| 开放与获取 | 公开处理数据（Apache-2.0）；[官方入口](https://biscue5.github.io/egovla-project-page/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| π0（EgoScalerV2） | 决策 / 动作 | 预训练 | 第一视角 RGB、任务文本与重建的物体状态 / 动作轨迹 | [论文](https://arxiv.org/abs/2509.21986)；[数据集](https://huggingface.co/datasets/Biscue5/egoscaler-v2) |

## 官方来源

- [论文](https://arxiv.org/abs/2509.21986)
- [项目页](https://biscue5.github.io/egovla-project-page/)
- [官方数据页](https://huggingface.co/datasets/Biscue5/egoscaler-v2)
