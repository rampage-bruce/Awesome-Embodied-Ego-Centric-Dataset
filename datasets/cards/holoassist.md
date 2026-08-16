# HoloAssist

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 机构 | Microsoft Research；ETH Zurich |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [HoloAssist: an Egocentric Human Interaction Dataset for Interactive AI Assistants in the Real World](https://openaccess.thecvf.com/content/ICCV2023/html/Wang_HoloAssist_an_Egocentric_Human_Interaction_Dataset_for_Interactive_AI_Assistants_ICCV_2023_paper.html) |
| 项目 / 数据 | [项目页](https://holoassist.github.io/)；[下载页](https://holoassist.github.io/#download) |
| 代码 | [Ember-HoloAssist/holoassist-release](https://github.com/Ember-HoloAssist/holoassist-release) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 受控真实环境 |
| 场景 | 工作间、办公室、家庭与专业实验室 |
| 采集设备 | Microsoft HoloLens 2；Platform for Situated Intelligence（Psi）采集系统 |
| 相机设置 | 人类第一视角：HoloLens 2 头显、移动、RGB-D |
| 实际采集数据 | 同步 RGB、AHAT 深度、3D 手部位姿、头部位姿、眼动、音频与 IMU；相机内外参与时间戳 |
| 已发布数据 | RGB-D；IMU；音频；眼动 |

## 监督信号与数据构建

- 位姿 / 眼动 / 深度 ← HoloLens 2 原生跟踪、传感器与 SLAM。
- 动作、错误、对话与摘要 ← 专业人工标注。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 当前项目页口径 169 小时（ICCV 2023 论文口径 166 小时）；2,221 个会话；222 名参与者；350 对讲解者—执行者组合；20 项任务 |
| 开放与获取 | 公开：数据、标注与代码；[官方入口](https://holoassist.github.io/) |

## 模态影响

- 细粒度动作识别从头训练时，在 RGB 上加入手部位姿后，Top-1 准确率从 18.78% 提升到 29.32%；简单加入全部传感器并不总能继续提升。
- 来源：[论文](https://openaccess.thecvf.com/content/ICCV2023/html/Wang_HoloAssist_an_Egocentric_Human_Interaction_Dataset_for_Interactive_AI_Assistants_ICCV_2023_paper.html)

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 第一视角片段经 EgoSmith 统一为训练样本；保留 11.5 小时 / 11,426 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| TimeSformer baseline | 预测 / 世界建模 | 训练 + 评测 | 第一视角视频及可选传感器用于下一动作、错误和干预类型预测 | [HoloAssist 论文](https://arxiv.org/abs/2309.17024)；[补充材料](https://openaccess.thecvf.com/content/ICCV2023/supplemental/Wang_HoloAssist_an_Egocentric_ICCV_2023_supplemental.pdf) |
| Seq2Seq hand-forecasting baseline | 预测 / 世界建模 | 训练 + 评测 | 历史 3D 手部关节序列用于预测未来 1.5 秒手部运动 | [HoloAssist 补充材料](https://openaccess.thecvf.com/content/ICCV2023/supplemental/Wang_HoloAssist_an_Egocentric_ICCV_2023_supplemental.pdf) |

## 官方来源

- 论文： [ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/html/Wang_HoloAssist_an_Egocentric_Human_Interaction_Dataset_for_Interactive_AI_Assistants_ICCV_2023_paper.html)；[补充材料](https://openaccess.thecvf.com/content/ICCV2023/supplemental/Wang_HoloAssist_an_Egocentric_ICCV_2023_supplemental.pdf)
- 项目页： [holoassist.github.io](https://holoassist.github.io/)
- 官方仓库： [Ember-HoloAssist/holoassist-release](https://github.com/Ember-HoloAssist/holoassist-release)
- 数据页： [官方下载](https://holoassist.github.io/#download)
- 文档： [Dataset and annotation structure](https://github.com/Ember-HoloAssist/holoassist-release#dataset-structure); [Microsoft Research overview](https://www.microsoft.com/en-us/research/?p=972234)
