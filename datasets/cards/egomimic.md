# EgoMimic

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 机构 | Georgia Institute of Technology; Stanford University |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 + 机器人对齐的人类数据 + 人机混合数据 |
| 论文 | [EgoMimic: Scaling Imitation Learning via Egocentric Video](https://arxiv.org/abs/2410.24221) |
| 项目 / 数据 | [项目页](https://egomimic.github.io/)；[数据集](https://huggingface.co/datasets/gatech/EgoMimic) |
| 代码 | [官方仓库](https://github.com/SimarKareer/EgoMimic) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 单手 / 双手 + 机器人夹爪 |
| 采集条件 | 受控真实环境 |
| 场景 | 室内桌面 / 家庭任务 |
| 采集设备 | 人类侧与机器人侧均使用 Project Aria；机器人另配两台腕部相机 |
| 相机设置 | 人类第一视角：头戴式、移动；机器人视角：固定躯干相机 + 移动腕部相机 |
| 实际采集数据 | 人类侧 Aria RGB、灰度场景视频、手部跟踪与 SLAM；机器人侧 Aria / 腕部 RGB、关节位置、末端位姿与动作 |
| 已发布数据 | 人类第一视角 RGB；机器人腕部 RGB；机器人本体状态 |

## 监督信号与数据构建

- 人类动作 / 相机位姿 ← Aria MPS 手部跟踪 + SLAM。
- 机器人动作 ← 遥操作日志 + 机器人运动学。
- 本体掩码 ← 投影位姿提示的 SAM 2。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 人类数据 4 小时 + 机器人数据 12 小时；2,150 个人类示范 + 1,000 个机器人示范；3 项任务 |
| 开放与获取 | 公开：处理数据、标签与代码；[官方入口](https://egomimic.github.io/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoMimic | 决策 / 动作 | 训练 + 评测 | 人类第一视角 RGB 与 MPS 生成的 3D 手部 / 末端轨迹，和机器人 RGB、本体状态及动作联合训练 | [论文](https://arxiv.org/abs/2410.24221)；[项目页](https://egomimic.github.io/) |

## 官方来源

- 论文：[arXiv](https://arxiv.org/abs/2410.24221)；[补充材料](https://egomimic.github.io/static/files/egomimic-supplementary.pdf)
- [项目页](https://egomimic.github.io/)
- [官方仓库](https://github.com/SimarKareer/EgoMimic)
- [数据页](https://huggingface.co/datasets/gatech/EgoMimic)
- 文档：[数据处理说明](https://github.com/SimarKareer/EgoMimic/blob/main/data_processing.md)；[Eve 硬件与采集代码](https://github.com/SimarKareer/EgoMimic-Eve)
