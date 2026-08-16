# Open-AoE

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 机构 | Ant Digital Technologies, Ant Group |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 + 机器人对齐的人类数据 |
| 论文 | [Open-AoE: An Open Egocentric Manipulation Dataset and Toolchain for Embodied Learning](https://arxiv.org/abs/2607.14183) |
| 项目 / 数据 | [Hugging Face](https://huggingface.co/datasets/inclusionAI/OpenAoE-2000h); [ModelScope](https://www.modelscope.cn/datasets/inclusionAI/OpenAoE-2000h) |
| 代码 | [Open-AoE](https://github.com/ant-research/Open-AoE) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 自然环境 |
| 场景 | 厨房、桌面、办公室与工作间等日常环境 |
| 采集设备 | 400 余种智能手机型号 |
| 相机设置 | 人类第一视角：穿戴式手机、移动、单目 RGB |
| 实际采集数据 | 单目 RGB；相机内参与设备元数据 |
| 已发布数据 | 原始与去畸变单目 RGB；相机标定；MANO 手部位姿；相机轨迹；原子动作标注 |

## 监督信号与数据构建

- 手部 / 手腕位姿 ← 检测器 + HaWoR + SLAM 对齐。
- 相机位姿 ← DROID-W + 全局光束法平差。
- 原子动作与英文描述 ← 自动语义标注 + 人工复核。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 完整版本约 2,000 小时；500 余名贡献者；400 余个场景；8,000 余项任务 |
| 开放与获取 | 截至 2026-08-12，nano / tiny 已发布，full 版本已上传约 694 小时且仍在分批上传；处理、重定向与训练代码公开；[官方入口](https://huggingface.co/datasets/inclusionAI/OpenAoE-2000h) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| VITRA Training-Ready recipe | 决策 / 动作 | 训练 | 将 Open-AoE 的 RGB、手部 / 相机运动和原子动作转换为 VITRA 所需状态—动作语义，并提供训练启动配置 | [Open-AoE 官方仓库](https://github.com/ant-research/Open-AoE) |
| DreamZero Training-Ready recipe | 预测 / 世界建模 | 训练 | 将 Open-AoE 片段转换为视频—动作世界模型所需格式，并提供训练配方 | [Open-AoE 官方仓库](https://github.com/ant-research/Open-AoE) |

## 官方来源

- [论文](https://arxiv.org/abs/2607.14183)
- [官方仓库](https://github.com/ant-research/Open-AoE)
- [官方数据页](https://huggingface.co/datasets/inclusionAI/OpenAoE-2000h)
- [数据格式文档](https://github.com/ant-research/Open-AoE/blob/main/open-aoe-2000h/README.md)
