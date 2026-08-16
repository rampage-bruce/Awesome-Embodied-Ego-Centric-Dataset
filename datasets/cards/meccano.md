# MECCANO 数据集家族

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2021 / 2023 |
| 机构 | FPV@IPLab, University of Catania；University of Hertfordshire（初始论文）；Next Vision s.r.l. |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [The MECCANO Dataset: Understanding Human-Object Interactions from Egocentric Videos in an Industrial-like Domain](https://arxiv.org/abs/2010.05654); [MECCANO: A Multimodal Egocentric Dataset for Humans Behavior Understanding in the Industrial-like Domain](https://arxiv.org/abs/2209.08691) |
| 项目 / 数据 | https://iplab.dmi.unict.it/legacy/MECCANO/; https://iplab.dmi.unict.it/legacy/MECCANO/#dataset |
| 代码 | https://github.com/fpv-iplab/MECCANO |

## 版本

### MECCANO

| 字段 | 内容 |
| --- | --- |
| 年份 | 2021 |
| 已发布数据 | 组装过程的第一视角 RGB 视频 / 帧 |
| 监督信号 | 动作 / EHOI、活动物体框、手框与交互边界 |
| 规模 | 20 次完整组装；8,857 个动作片段 |

### MECCANO Multimodal

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 已发布数据 | 同一批 20 个序列，增加时间对齐的深度与眼动 |
| 监督信号 | 原动作 / 物体标签，以及眼动与下一活动物体 |
| 规模 | 20 个序列；301,016 个对齐深度帧 |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 受控真实环境 |
| 场景 | 工业式桌面玩具组装 |
| 采集设备 | Intel RealSense SR300 与 Pupil Labs Pupil Core 组成的头戴采集架 |
| 相机设置 | 人类第一视角：头戴式、移动、RGB-D；头显集成眼动 |
| 实际采集数据 | 同步单目 RGB、深度与眼动 |
| 已发布数据 | 单目 RGB-D；眼动 |

## 监督信号与数据构建

- 动作 / 活动物体 ← 人工标注。
- 手框 ← 100 Days of Hands + 人工修正。
- 交互边界 ← 人工标注 + 时间规则。
- 深度 / 眼动 ← 设备采集 + 时间对齐。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 20 段视频；8,857 个动作片段；20 名参与者；1 项组装任务；61 个动作类别 |
| 开放与获取 | 公开：数据、标注与代码；[官方入口](https://iplab.dmi.unict.it/legacy/MECCANO/) |

## 模态影响

- Multimodal SlowFast 中，RGB 与深度的 Top-1 分别为 45.16% 和 45.13%；RGB + 深度为 49.49%，再加入眼动后为 49.66%。
- 来源：[多模态版本论文](https://arxiv.org/abs/2209.08691)

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| SlowFast EHOI baseline | 具身感知 | 训练 + 评测 | RGB 或深度视频、动词及活动物体标注用于第一视角手—物交互检测 | [MECCANO 官方仓库](https://github.com/fpv-iplab/MECCANO#3-egocentric-human-object-interaction-ehoi-detection) |
| RU-LSTM | 预测 / 世界建模 | 训练 + 评测 | 物体、眼动和手部特征用于预测下一项操作动作 | [MECCANO 官方仓库](https://github.com/fpv-iplab/MECCANO#4-action-anticipation) |

## 官方来源

- 论文： [WACV 2021](https://arxiv.org/abs/2010.05654)；[多模态版本 / CVIU 2023](https://arxiv.org/abs/2209.08691)
- 项目页： https://iplab.dmi.unict.it/legacy/MECCANO/
- 官方仓库： https://github.com/fpv-iplab/MECCANO
- 数据页： https://iplab.dmi.unict.it/legacy/MECCANO/#dataset
- 文档： [下载清单](https://iplab.dmi.unict.it/legacy/MECCANO/#dataset)；[基准代码](https://github.com/fpv-iplab/MECCANO)
