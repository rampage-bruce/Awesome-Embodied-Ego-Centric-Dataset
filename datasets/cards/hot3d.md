# HOT3D

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Meta Reality Labs |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [HOT3D: Hand and Object Tracking in 3D from Egocentric Multi-View Videos](https://openaccess.thecvf.com/content/CVPR2025/html/Banerjee_HOT3D_Hand_and_Object_Tracking_in_3D_from_Egocentric_Multi-View_CVPR_2025_paper.html) |
| 项目 / 数据 | https://facebookresearch.github.io/hot3d/; https://www.projectaria.com/datasets/hot3d/ |
| 代码 | https://github.com/facebookresearch/hot3d |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 实验室 |
| 场景 | 检查、厨房、办公室与客厅 |
| 采集设备 | Project Aria；开发者模式 Meta Quest 3；外部 OptiTrack 红外动捕系统 |
| 相机设置 | 人类第一视角：Aria / Quest 多相机头显、移动；外部动捕相机固定 |
| 实际采集数据 | 头显多视角图像与光学动捕；Aria 含 RGB、双灰度与眼动相机；Quest 发布双前向灰度视角 |
| 已发布数据 | Aria RGB 与多视角灰度视频；Quest 多视角灰度视频；眼动；物体网格；SLAM 几何 |

## 监督信号与数据构建

- 手部位姿 ← 光学动捕 + 个性化 UmeTrack / MANO 拟合。
- 相机位姿 ← Aria MPS 或头显动捕。
- 物体位姿 ← 光学动捕与扫描模型配准。
- 眼动 ← Aria MPS。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 833 分钟；425 段记录；150 万个多视角帧；370 万余张图像；4 类场景 |
| 开放与获取 | 受限访问：数据、标注与工具包；[官方入口](https://facebookresearch.github.io/hot3d/) |

## 模态影响

- 在 HOT3D-Quest3 上，UmeTrack 使用双视角时手部 MPKE 从单视角的 15.4 mm 降至 10.9 mm。
- 来源：[论文](https://openaccess.thecvf.com/content/CVPR2025/html/Banerjee_HOT3D_Hand_and_Object_Tracking_in_3D_from_Egocentric_Multi-View_CVPR_2025_paper.html)

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 第一视角片段经 EgoSmith 统一为训练样本；保留 4.5 小时 / 1,105 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| UmeTrack | 具身感知 | 评测 | 单视角和多视角头显图像用于 3D 手部位姿跟踪评测 | [HOT3D 论文](https://arxiv.org/abs/2411.19167) |
| FoundPose | 具身感知 | 评测 | 单视角与多视角图像、物体 CAD 模型用于 6DoF 物体位姿估计评测 | [HOT3D 论文](https://arxiv.org/abs/2411.19167) |

## 官方来源

- 论文： [CVPR 2025](https://openaccess.thecvf.com/content/CVPR2025/html/Banerjee_HOT3D_Hand_and_Object_Tracking_in_3D_from_Egocentric_Multi-View_CVPR_2025_paper.html)；[arXiv](https://arxiv.org/abs/2411.19167)
- 项目页： https://facebookresearch.github.io/hot3d/
- 官方仓库： https://github.com/facebookresearch/hot3d
- 数据页： https://www.projectaria.com/datasets/hot3d/; [HOT3D-Clips](https://huggingface.co/datasets/bop-benchmark/hot3d)
- 文档： [HOT3D 工具包](https://github.com/facebookresearch/hot3d#readme)；[发布版本](https://github.com/facebookresearch/hot3d/blob/main/VERSIONS.md)；[HOT3D-Clips](https://github.com/facebookresearch/hot3d/blob/main/hot3d/clips/README.md)；[许可证](https://www.projectaria.com/datasets/hot3d/license/)
