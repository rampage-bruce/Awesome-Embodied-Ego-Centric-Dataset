# Ego4D

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2021 |
| 机构 | Ego4D Consortium（Meta AI / FAIR 牵头，国际高校合作采集） |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [Ego4D: Around the World in 3,000 Hours of Egocentric Video](https://openaccess.thecvf.com/content/CVPR2022/html/Grauman_Ego4D_Around_the_World_in_3000_Hours_of_Egocentric_Video_CVPR_2022_paper.html) |
| 项目 / 数据 | [项目与数据页](https://ego4d-data.org/)；[数据文档](https://ego4d-data.org/docs/) |
| 代码 | [facebookresearch/Ego4d](https://github.com/facebookresearch/Ego4d) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 人手 |
| 采集条件 | 自然与设计采集混合 |
| 场景 | 家庭、户外、工作、休闲与社交 |
| 采集设备 | GoPro、Vuzix Blade、Pupil Labs、ZShades、ORDRO EP6、iVue Rincon 1080 与 Weeview 等头戴设备 |
| 相机设置 | 人类第一视角：头戴式、移动；含同步多第一视角子集 |
| 实际采集数据 | 第一视角 RGB；部分子集含音频、双目 RGB、IMU、眼动、同步多第一视角、第三视角与环境 3D 扫描 |
| 已发布数据 | RGB；部分样本含音频、双目 RGB、IMU、眼动、多视角数据与 3D 扫描 |

## 监督信号与数据构建

- 旁白 ← 标注员为视频片段划定时间区间并撰写英文行为描述，同时撰写整段视频摘要。
- 手框 ← 预训练 100DOH 检测器生成初始框，再由标注员修正或补画。
- 物体 / 工具框与角色 ← 标注员逐帧绘制并选择物体名称、实例 ID 和交互角色。
- PRE / CONTACT / PNR / POST 关键帧、动作动词与状态变化类型 ← 分阶段人工标注。
- 3D 子集 ← 扫描与重建。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 3,670 小时；74 个地点；9 个国家；5 类基准任务 |
| 开放与获取 | 受限访问：数据、标注与代码；[官方入口](https://ego4d-data.org/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| VITRA-VLA | 决策 / 动作 | 预训练 | 仅使用 Ego4D 原始 RGB；VITRA 生成原子语言与 3D 手部 / 相机动作，两个子集共 948,683 个片段 | [VITRA 论文](https://arxiv.org/abs/2510.21571)；[官方仓库](https://github.com/microsoft/VITRA) |
| π0（EgoScalerV2） | 决策 / 动作 | 预训练 | Ego4D RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | [EgoScalerV2 论文](https://arxiv.org/abs/2509.21986) |
| EgoSteer | 决策 / 动作 | 预训练 | VITRA 筛选的 Ego4D 片段，经处理得到 RGB-D、手部动作、相机参数与语言；保留 138 小时 / 74,505 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| R3M | 表征学习 | 预训练 | Ego4D 视频与语言用于时间对比、视频—语言对齐预训练；所得视觉表示作为机器人策略的冻结感知模块 | [R3M 论文](https://arxiv.org/abs/2203.12601)；[官方仓库](https://github.com/facebookresearch/r3m) |
| EgoVLP | 表征学习 | 预训练 + 微调 + 评测 | 从 Ego4D 构建 380 万视频—文本对进行预训练，并在 Ego4D 的语言查询、时刻查询和物体状态变化任务上微调与评测 | [EgoVLP 论文](https://arxiv.org/abs/2206.01670) |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 948,683 个片段经筛选和手部重建，得到 216.6 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- 论文： [CVPR 2022](https://openaccess.thecvf.com/content/CVPR2022/html/Grauman_Ego4D_Around_the_World_in_3000_Hours_of_Egocentric_Video_CVPR_2022_paper.html)；[补充材料](https://openaccess.thecvf.com/content/CVPR2022/supplemental/Grauman_Ego4D_Around_the_CVPR_2022_supplemental.pdf)
- 项目页： [ego4d-data.org](https://ego4d-data.org/)
- 官方仓库： [facebookresearch/Ego4d](https://github.com/facebookresearch/Ego4d)
- 数据页： [数据文档](https://ego4d-data.org/docs/)
- 文档： [元数据](https://ego4d-data.org/docs/data/metadata/)；[标注流程](https://ego4d-data.org/docs/data/annotation-guidelines/)；[Hands & Objects](https://ego4d-data.org/docs/benchmarks/hands-and-objects/)；[未处理数据](https://ego4d-data.org/docs/data/unprocessed_data/)；[版本更新](https://ego4d-data.org/docs/updates/)
