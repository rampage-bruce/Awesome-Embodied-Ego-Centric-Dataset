# Ego-Exo4D

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 机构 | Meta 与 12 家合作研究机构组成的联合团队 |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [Ego-Exo4D: Understanding Skilled Human Activity from First- and Third-Person Perspectives](https://openaccess.thecvf.com/content/CVPR2024/html/Grauman_Ego-Exo4D_Understanding_Skilled_Human_Activity_from_First-_and_Third-Person_Perspectives_CVPR_2024_paper.html) |
| 项目 / 数据 | https://ego-exo4d-data.org/; https://docs.ego-exo4d-data.org/ |
| 代码 | https://github.com/facebookresearch/Ego4d |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 人手 |
| 采集条件 | 受控真实环境 |
| 场景 | 体育、音乐、舞蹈、烹饪、维修与健康活动 |
| 采集设备 | 每套采集通常包含 1 台 Project Aria 与 4–5 台 GoPro |
| 相机设置 | 人类第一视角：头戴式、移动；第三视角：多台固定相机 |
| 实际采集数据 | Aria RGB、双灰度 SLAM 视频、7 通道音频、双 IMU、眼动，以及同步多视角 GoPro RGB / 音频 |
| 已发布数据 | 第一视角 RGB；Aria 灰度 SLAM 视频；多视角第三视角 RGB；音频；IMU；眼动 |

## 监督信号与数据构建

- 手部 / 身体位姿 ← 人工或模型关键点 + 多视角三角化。
- 相机位姿 ← Aria MPS / SLAM。
- 分割 ← 人工提示 + 模型辅助。
- 关键步骤 / 语言 ← 人工与专家标注。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 总视频 1,286.30 小时，其中第一视角 221.26 小时；5,035 次采集；8 类活动 |
| 开放与获取 | 受限访问：数据、标注与代码；[官方入口](https://ego-exo4d-data.org/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| VITRA-VLA | 决策 / 动作 | 预训练 | 第一视角 RGB 经处理生成原子语言与 3D 手部 / 相机动作，共 67,053 个片段 | [VITRA 论文](https://arxiv.org/abs/2510.21571)；[官方仓库](https://github.com/microsoft/VITRA) |
| π0（EgoScalerV2） | 决策 / 动作 | 预训练 | 第一视角 RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | [EgoScalerV2 论文](https://arxiv.org/abs/2509.21986) |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 41,414 个第一视角片段经筛选和手部重建，得到 10.3 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- 论文： [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Grauman_Ego-Exo4D_Understanding_Skilled_Human_Activity_from_First-_and_Third-Person_Perspectives_CVPR_2024_paper.html)；[补充材料](https://openaccess.thecvf.com/content/CVPR2024/supplemental/Grauman_Ego-Exo4D_Understanding_Skilled_CVPR_2024_supplemental.pdf)；[arXiv](https://arxiv.org/abs/2311.18259)；[IJCV 2025 扩展版](https://doi.org/10.1007/s11263-025-02557-6)
- 项目页： https://ego-exo4d-data.org/
- 官方仓库： https://github.com/facebookresearch/Ego4d
- 数据页： https://docs.ego-exo4d-data.org/
- 文档： [Overview](https://docs.ego-exo4d-data.org/overview/); [MPS](https://docs.ego-exo4d-data.org/data/mps/); [Annotations](https://docs.ego-exo4d-data.org/annotations/); [EgoPose](https://docs.ego-exo4d-data.org/annotations/ego_pose/); [Relations](https://docs.ego-exo4d-data.org/annotations/relations/); [Expert Commentary](https://docs.ego-exo4d-data.org/annotations/expert_commentary/); [Getting Started](https://docs.ego-exo4d-data.org/getting-started/); [V2 changelog](https://docs.ego-exo4d-data.org/changelog/)
