# VITRA-1M

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Tsinghua University; Microsoft Research Asia |
| 数据角色 | 机器人对齐的人类数据 |
| 论文 | [Scalable Vision-Language-Action Model Pretraining for Robotic Manipulation with Real-Life Human Activity Videos](https://arxiv.org/abs/2510.21571) |
| 项目 / 数据 | [项目页](https://microsoft.github.io/VITRA/)；[数据集](https://huggingface.co/datasets/VITRA-VLA/VITRA-1M) |
| 代码 | [官方仓库](https://github.com/microsoft/VITRA) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 取决于聚合源数据 |
| 场景 | 烹饪、清洁、施工、维修与手工制作 |
| 采集设备 | 沿用 Ego4D、EPIC-KITCHENS、Ego-Exo4D 与 Something-Something-V2 的采集设备 |
| 相机设置 | 视角取决于源数据：主要为穿戴式 / 移动第一视角；另含非第一视角 SSV2 视频 |
| 实际采集数据 | 4 个源数据集的 RGB 视频；VITRA-1M 不新增传感器采集 |
| 已发布数据 | 分段语言；相机内外参；左右手 MANO / 运动轨迹；源帧索引；原始视频需从源数据获取 |

## 监督信号与数据构建

- 手部运动 ← HaWoR。
- 相机运动 ← 改进 MegaSAM + MoGe-2。
- 动作 ← 相机坐标系中的重建运动。
- 语言 ← GPT-4.1。
- 片段边界 ← 手腕速度极小值。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 1,222,918 个片段；2,600 万帧 |
| 开放与获取 | 公开：处理后标注与代码（MIT）；原始视频沿用源数据访问条款；[官方入口](https://microsoft.github.io/VITRA/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| VITRA-VLA | 决策 / 动作 | 预训练 | RGB 观测、语言指令与重建的 3D 手部状态 / 动作序列 | [论文](https://arxiv.org/abs/2510.21571)；[训练代码](https://github.com/microsoft/VITRA) |

## 官方来源

- [论文](https://arxiv.org/abs/2510.21571)
- [项目页](https://microsoft.github.io/VITRA/)
- 代码与数据统计：[官方仓库](https://github.com/microsoft/VITRA)
- [VITRA-1M 数据集](https://huggingface.co/datasets/VITRA-VLA/VITRA-1M)
