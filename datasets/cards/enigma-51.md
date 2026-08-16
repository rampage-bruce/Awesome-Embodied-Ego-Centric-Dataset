# ENIGMA-51

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 机构 | FPV@IPLab, University of Catania; Next Vision s.r.l. |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [ENIGMA-51: Towards a Fine-Grained Understanding of Human-Object Interactions in Industrial Scenarios](https://arxiv.org/abs/2309.14809) |
| 项目 / 数据 | https://fpv-iplab.github.io/ENIGMA-51/; https://fpv-iplab.github.io/ENIGMA-51/#download |
| 代码 | https://github.com/fpv-iplab/ENIGMA-51 |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 受控真实环境 |
| 场景 | 工业实验室 / 电气板维修 |
| 采集设备 | Microsoft HoloLens 2 与定制 Unity 指导应用 |
| 相机设置 | 人类第一视角：头戴式、移动、单目 RGB |
| 实际采集数据 | 单目 RGB 与指导步骤时间戳 |
| 已发布数据 | RGB；抽取帧；3D 物体 / 场景模型；衍生特征 |

## 监督信号与数据构建

- 手部关键点 ← MMPose。
- 手框 ← 100 Days of Hands + 人工修正。
- 掩码 ← SAM-HQ。
- 交互 / 物体框 ← 人工标注。
- 接触 / 接触时间 ← 事件标注 + 时间规则。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 22 小时；51 段视频；19 名参与者；14,036 次交互；2 套维修流程 |
| 开放与获取 | 公开：数据、标注、衍生标签与代码；[官方入口](https://fpv-iplab.github.io/ENIGMA-51/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| egoism-hoi | 具身感知 | 训练 + 评测 | 第一视角帧、手部和活动物体标注用于检测当前手—物交互 | [ENIGMA-51 官方仓库](https://github.com/fpv-iplab/ENIGMA-51#egocentric-human-object-interaction-detection) |
| StillFast | 预测 / 世界建模 | 训练 + 评测 | 第一视角视频与交互标注用于短期物体交互预判 | [ENIGMA-51 官方仓库](https://github.com/fpv-iplab/ENIGMA-51#short-term-object-interaction-anticipation) |

## 官方来源

- 论文： [WACV 2024 paper and supplementary](https://arxiv.org/abs/2309.14809)
- 项目页： https://fpv-iplab.github.io/ENIGMA-51/
- 官方仓库： https://github.com/fpv-iplab/ENIGMA-51
- 数据页： https://fpv-iplab.github.io/ENIGMA-51/#download
- 文档： [数据与下载说明](https://fpv-iplab.github.io/ENIGMA-51/)；[基准代码](https://github.com/fpv-iplab/ENIGMA-51)
