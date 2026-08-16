# EgoExoLearn

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 机构 | OpenGVLab / Shanghai AI Laboratory; Nanjing University; Shenzhen Institutes of Advanced Technology, CAS; University of Tokyo; Fudan University; Zhejiang University; University of Science and Technology of China |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [EgoExoLearn: A Dataset for Bridging Asynchronous Ego- and Exo-centric View of Procedural Activities in Real World](https://openaccess.thecvf.com/content/CVPR2024/html/Huang_EgoExoLearn_A_Dataset_for_Bridging_Asynchronous_Ego-_and_Exo-centric_View_CVPR_2024_paper.html) |
| 项目 / 数据 | [项目页](https://egoexolearn.github.io/)；[Hugging Face 数据页](https://huggingface.co/datasets/hyf015/EgoExoLearn) |
| 代码 | https://github.com/OpenGVLab/EgoExoLearn |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 混合采集 |
| 场景 | 厨房与专业实验室 |
| 采集设备 | Pupil Invisible 眼动眼镜；在线第三视角视频使用不同来源相机 |
| 相机设置 | 人类第一视角：头戴式、移动；第三视角：非同步视频 |
| 实际采集数据 | Pupil Invisible 第一视角 RGB 与 120 Hz 眼动；另有非同步第三视角示范视频 |
| 已发布数据 | 单目第一视角 RGB；非同步第三视角 RGB；眼动 |

## 监督信号与数据构建

- 动作 / 跨视角配对 ← 人工标注。
- 眼动 ← 设备采集 + 标定。
- 描述文本 ← 人工标注 + 机器翻译 + 人工质检。
- 技能 ← 多人标注 + 一致性过滤。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 120 小时（第一视角 96.5 小时 + 第三视角 23.5 小时）；747 段视频；约 7.8 万个细粒度片段；8 项流程任务 |
| 开放与获取 | 公开：数据、标注、特征与代码；[官方入口](https://egoexolearn.github.io/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| TimeSformer–CLIP cross-view association baseline | 表征学习 | 训练 + 评测 | 异步第一 / 第三视角视频与描述文本用于学习跨视角视频—文本对应关系 | [EgoExoLearn 论文](https://arxiv.org/abs/2403.16182)；[官方仓库](https://github.com/OpenGVLab/EgoExoLearn) |
| CLIP + TA3N anticipation / planning baseline | 预测 / 世界建模 | 训练 + 评测 | 第一 / 第三视角视频、动作标签及可选眼动用于预测下一动作和后续 8 个流程步骤 | [EgoExoLearn 论文](https://arxiv.org/abs/2403.16182) |

## 官方来源

- 论文： [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Huang_EgoExoLearn_A_Dataset_for_Bridging_Asynchronous_Ego-_and_Exo-centric_View_CVPR_2024_paper.html)；[arXiv 与补充材料](https://arxiv.org/html/2403.16182)
- 项目页： https://egoexolearn.github.io/
- 官方仓库： https://github.com/OpenGVLab/EgoExoLearn
- 数据页： [Hugging Face](https://huggingface.co/datasets/hyf015/EgoExoLearn)
- 文档： [数据获取与基准目录](https://github.com/OpenGVLab/EgoExoLearn)；[发布文件](https://huggingface.co/datasets/hyf015/EgoExoLearn/tree/main)
