# UniHand-2.0

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 机构 | BeingBeyond |
| 数据角色 | 带标注的人类第一视角数据 + 机器人对齐的人类数据 + 人机混合数据 |
| 论文 | [Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization](https://arxiv.org/abs/2601.12993) |
| 项目 / 数据 | [项目页](https://research.beingbeyond.com/being-h05)；[UniHand 预览数据](https://huggingface.co/datasets/BeingBeyond/UniHand_Preview) |
| 代码 | [Being-H](https://github.com/BeingBeyond/Being-H) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 + 30 种机器人本体 |
| 采集条件 | 取决于真实、仿真及聚合源数据 |
| 场景 | 家庭、烹饪、工业、桌面机器人、仿真与 VLM 场景 |
| 采集设备 | 设备取决于源数据；UniCraftor 使用头戴式 RealSense D435、可移动 D435、AprilTag 与同步脚踏开关 |
| 相机设置 | 视角取决于源数据：人类头戴移动第一视角，以及机器人第一视角 / 腕部 / 第三视角 |
| 实际采集数据 | 人类第一视角 RGB / RGB-D；机器人多视角 RGB 与状态 / 动作；仿真与图像 / 视频文本数据 |
| 已发布数据 | 公开预览子集：第一视角 RGB、相机位姿、左右手 MANO / 手腕运动、指令与描述；另含部分机器人和视觉语言数据 |

## 监督信号与数据构建

- 人体运动 ← HaWoR + 相机几何 / 过滤。
- 人类视频语言 ← Gemini-2.5。
- UniCraftor 语言 ← Qwen2.5-VL + 人工核验。
- 机器人动作 ← 源日志 / 仿真 + 统一映射。
- 训练目标 ← 连续动作 + 运动 token。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 训练配方：35K+ 小时；400M+ 样本；120B+ token；其中 16K 小时人类、14K 小时机器人、5K 等效小时 VLM 数据 |
| 开放与获取 | 公开预览子集与训练 / 数据准备代码；预览不等同完整训练语料；[官方入口](https://research.beingbeyond.com/being-h05) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| Being-H0.5 | 决策 / 动作 | 预训练 | 人类第一视角视频、手部运动 / 语言、多本体机器人观测 / 动作与视觉语言监督 | [论文](https://arxiv.org/abs/2601.12993)；[官方仓库](https://github.com/BeingBeyond/Being-H) |

## 官方来源

- [论文](https://arxiv.org/abs/2601.12993)
- [项目页](https://research.beingbeyond.com/being-h05)
- [官方仓库](https://github.com/BeingBeyond/Being-H)
- 预览数据：[UniHand](https://huggingface.co/datasets/BeingBeyond/UniHand_Preview)
