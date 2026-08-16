# EgoDex

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Apple |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 + 机器人对齐的人类数据 |
| 论文 | [EgoDex: Learning Dexterous Manipulation from Large-Scale Egocentric Video](https://arxiv.org/abs/2505.11709) |
| 项目 / 数据 | [Apple Machine Learning Research](https://machinelearning.apple.com/research/egodex-learning-dexterous-manipulation)；[数据获取与结构](https://github.com/apple/ml-egodex#dataset-access-and-download) |
| 代码 | [apple/ml-egodex](https://github.com/apple/ml-egodex) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 受控真实环境 |
| 场景 | 家庭桌面操作 |
| 采集设备 | Apple Vision Pro（visionOS 2）与 ARKit |
| 相机设置 | 人类第一视角：Apple Vision Pro 头显、移动、单目 RGB |
| 实际采集数据 | 第一视角 RGB；相机内外参；上半身、手腕、手与手指 3D 关节变换；关节置信度；任务 / 环境 / 物体元数据 |
| 已发布数据 | 单目 RGB；跟踪骨架 / 位姿；相机标定 / 轨迹；任务 / 语言元数据 |

## 监督信号与数据构建

- 手部 / 手腕 / 身体位姿 ← ARKit 跟踪。
- 相机位姿 ← ARKit SLAM。
- 片段边界 ← 采集控制。
- 语言 ← 采集者元数据 + GPT-4 生成 / 选择。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 829 小时；338,000 个片段；9,000 万帧；194 项任务 |
| 开放与获取 | 公开：数据、标注与示例代码；[官方入口](https://machinelearning.apple.com/research/egodex-learning-dexterous-manipulation) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 使用 EgoDex 原生 RGB、手部 / 相机位姿与语言；EgoSmith 补充深度并统一格式；保留 370 小时 / 147,588 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 327,317 个片段经筛选和动作统一，得到 776.8 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- 论文： [EgoDex: Learning Dexterous Manipulation from Large-Scale Egocentric Video](https://arxiv.org/abs/2505.11709)
- 项目页： [Apple Machine Learning Research](https://machinelearning.apple.com/research/egodex-learning-dexterous-manipulation)
- 官方仓库： [apple/ml-egodex](https://github.com/apple/ml-egodex)
- 数据页： [数据获取与下载](https://github.com/apple/ml-egodex#dataset-access-and-download)
- 文档： [数据结构](https://github.com/apple/ml-egodex#dataset-structure)
