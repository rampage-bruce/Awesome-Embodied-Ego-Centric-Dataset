# EgoVerse

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 机构 | Georgia Institute of Technology；Stanford University；UC San Diego；ETH Zürich；MIT CSAIL；Meta Reality Labs Research；产业合作方 |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 + 机器人对齐的人类数据 |
| 论文 | [EgoVerse: An Egocentric Human Dataset for Robot Learning from Around the World](https://arxiv.org/abs/2604.07607) |
| 项目 / 数据 | [项目与数据浏览器](https://egoverse.ai/) |
| 代码 | [官方仓库](https://github.com/GaTech-RL2/EgoVerse) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 混合采集 |
| 场景 | 多实验室操作与工业活动 |
| 采集设备 | Project Aria Gen 1；头戴式 iPhone 超广角相机；合作方定制穿戴设备 |
| 相机设置 | 人类第一视角：头戴 / 移动；传感器配置随来源而异 |
| 实际采集数据 | 按设备包含 Aria RGB / 灰度 / IMU、手机单目 RGB，或合作方双目 RGB / 深度 / IMU |
| 已发布数据 | 第一视角 RGB；部分来源含其他传感器流 |

## 监督信号与数据构建

- 手部位姿 ← 原生跟踪或合作方模型估计 + 平滑。
- 相机位姿 ← MPS / SLAM 或合作方跟踪。
- 动作代理 ← 相机坐标系中的未来手部轨迹。
- 任务 / 语言 ← 源数据元数据与标注流程。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 1,362 小时；约 8 万个片段；1,965 项任务；2,087 名示范者 |
| 开放与获取 | 公开：数据及处理 / 训练代码；[官方入口](https://egoverse.ai/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoVerse cross-embodiment policy | 决策 / 动作 | 训练 + 评测 | 第一视角 RGB、相机坐标系中的未来手部轨迹与任务语言，和机器人轨迹联合训练 | [论文](https://arxiv.org/abs/2604.07607) |
| EgoSteer | 决策 / 动作 | 预训练 | 使用原生手部 / 相机标注；EgoSmith 补充深度和语言并统一格式；保留 690 小时 / 35,175 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |

## 官方来源

- [论文](https://arxiv.org/abs/2604.07607)
- 项目与数据浏览器：[EgoVerse](https://egoverse.ai/)
- 处理与训练代码：[官方仓库](https://github.com/GaTech-RL2/EgoVerse)
- 使用论文：[EgoSteer](https://arxiv.org/abs/2607.09701)
