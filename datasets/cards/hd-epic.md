# HD-EPIC

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | University of Bristol; Leiden University; Singapore Management University; University of Bath |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [HD-EPIC: A Highly-Detailed Egocentric Video Dataset](https://openaccess.thecvf.com/content/CVPR2025/html/Perrett_HD-EPIC_A_Highly-Detailed_Egocentric_Video_Dataset_CVPR_2025_paper.html) |
| 项目 / 数据 | https://hd-epic.github.io/site/; https://data.bris.ac.uk/data/dataset/3cqb5b81wk2dc2379fx1mrxh47 |
| 代码 | [标注](https://github.com/hd-epic/hd-epic-annotations)；[下载工具](https://github.com/hd-epic/hd-epic-downloader) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 自然环境 |
| 场景 | 家庭厨房 |
| 采集设备 | Project Aria；电子秤与智能手机用于营养记录 |
| 相机设置 | 人类第一视角：头戴式 Project Aria、移动 |
| 实际采集数据 | 1 路前向 RGB、2 路灰度 SLAM 视频、7 路麦克风与眼动相机 |
| 已发布数据 | 单目 RGB；灰度 SLAM 视频；音频；眼动；3D 几何 |

## 监督信号与数据构建

- 相机位姿 / 几何 ← MPS，失败片段使用 COLMAP。
- 旁白 ← 佩戴者口述 + ASR + 人工核验。
- 掩码 ← SAM2 + 人工修正。
- 3D 物体位置 ← 预测深度 + MPS + 人工核验。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 41.3 小时；156 段视频；446 万帧；59,454 个动作；69 个食谱；约 2.6 万条 VQA 问题 |
| 开放与获取 | 公开：数据、标注与下载工具；[官方入口](https://hd-epic.github.io/site/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| π0（EgoScalerV2） | 决策 / 动作 | 预训练 | HD-EPIC RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | [EgoScalerV2 论文](https://arxiv.org/abs/2509.21986) |

## 官方来源

- 论文： [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Perrett_HD-EPIC_A_Highly-Detailed_Egocentric_Video_Dataset_CVPR_2025_paper.html)；[CVF PDF](https://openaccess.thecvf.com/content/CVPR2025/papers/Perrett_HD-EPIC_A_Highly-Detailed_Egocentric_Video_Dataset_CVPR_2025_paper.pdf)；[补充材料](https://openaccess.thecvf.com/content/CVPR2025/supplemental/Perrett_HD-EPIC_A_Highly-Detailed_CVPR_2025_supplemental.pdf)；[arXiv](https://arxiv.org/abs/2502.04144)
- 项目页： https://hd-epic.github.io/site/
- 官方仓库： [标注](https://github.com/hd-epic/hd-epic-annotations)；[下载工具](https://github.com/hd-epic/hd-epic-downloader)
- 数据页： [University of Bristol data record](https://data.bris.ac.uk/data/dataset/3cqb5b81wk2dc2379fx1mrxh47); DOI: [10.5523/bris.3cqb5b81wk2dc2379fx1mrxh47](https://doi.org/10.5523/bris.3cqb5b81wk2dc2379fx1mrxh47)
- 文档： [标注格式](https://github.com/hd-epic/hd-epic-annotations#readme)；[下载说明](https://github.com/hd-epic/hd-epic-downloader#readme)；[中间数据](https://github.com/hd-epic/hd-epic-annotations#hd-epic-intermediate-data)
