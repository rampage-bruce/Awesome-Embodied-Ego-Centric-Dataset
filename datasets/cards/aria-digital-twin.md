# Aria Digital Twin (ADT)

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 机构 | Meta Reality Labs Research |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [Aria Digital Twin: A New Benchmark Dataset for Egocentric 3D Machine Perception](https://openaccess.thecvf.com/content/ICCV2023/html/Pan_Aria_Digital_Twin_A_New_Benchmark_Dataset_for_Egocentric_3D_ICCV_2023_paper.html) |
| 项目 / 数据 | https://www.projectaria.com/datasets/adt/; https://explorer.projectaria.com/adt |
| 代码 | https://github.com/facebookresearch/projectaria_tools |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 人手 |
| 采集条件 | 实验室 / 受控真实环境 |
| 场景 | 数字化公寓与办公室 |
| 采集设备 | Project Aria；OptiTrack 动捕系统；FARO 房间扫描仪；ATOS 物体扫描仪；摄影测量系统 |
| 相机设置 | 真实采集：头戴式人类第一视角、移动，固定动捕系统；生成视角：数字孪生渲染 RGB / 深度 |
| 实际采集数据 | 1 路 Aria RGB、2 路灰度 SLAM 视频、双 IMU、眼动相机、OptiTrack 标记与高分辨率房间 / 物体扫描 |
| 已发布数据 | 第一视角 RGB 与双灰度视频；双 IMU；眼动；生成深度 / RGB；物体模型；场景几何 |

## 监督信号与数据构建

- 相机 / 身体 / 物体位姿 ← OptiTrack + 标定 / 扫描配准。
- 框 / 掩码 / 深度 / 合成 RGB ← 数字孪生渲染。
- 眼动 ← 眼动跟踪 + 几何。
- 场景几何 ← 扫描 + MPS。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | V2：8.13 小时、236 个设备序列；8 项设计活动 |
| 开放与获取 | 受限访问：数据、标签、物体模型与工具包；[官方入口](https://www.projectaria.com/datasets/adt/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| ViT-Det | 具身感知 | 评测 | 校正后的 Aria RGB 与 2D 框 / 实例掩码用于第一视角物体检测和分割评测 | [ADT 论文](https://arxiv.org/abs/2306.06362) |
| Cube R-CNN | 具身感知 | 评测 | 校正后的 Aria RGB 与 3D 物体框用于单目 3D 物体检测评测 | [ADT 论文](https://arxiv.org/abs/2306.06362) |

## 官方来源

- 论文： [ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/html/Pan_Aria_Digital_Twin_A_New_Benchmark_Dataset_for_Egocentric_3D_ICCV_2023_paper.html)；[arXiv](https://arxiv.org/html/2306.06362)
- 项目页： https://www.projectaria.com/datasets/adt/
- 官方仓库： https://github.com/facebookresearch/projectaria_tools
- 数据页： https://explorer.projectaria.com/adt
- 文档： [概览](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset)；[数据格式](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset/data_format)；[下载](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset/dataset_download)；[物体模型](https://facebookresearch.github.io/projectaria_tools/docs/open_datasets/aria_digital_twin_dataset/object_models)
