# EPIC-KITCHENS 数据集家族

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2018 |
| 机构 | University of Bristol；University of Catania；University of Toronto（初始版本）；后续资源另有 University of Michigan 等机构参与 |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 论文 | [Scaling Egocentric Vision: The EPIC-KITCHENS Dataset](https://arxiv.org/abs/1804.02748); [Rescaling Egocentric Vision: Collection, Pipeline and Challenges for EPIC-KITCHENS-100](https://arxiv.org/abs/2006.13256) |
| 项目 / 数据 | [官方主页](https://epic-kitchens.github.io/)；[EPIC-KITCHENS-100 数据页](https://data.bris.ac.uk/data/dataset/2g1n6qdydwa9u22shpxqzp0t8m) |
| 代码 | [官方 GitHub 组织](https://github.com/epic-kitchens)；[EK-100 标注](https://github.com/epic-kitchens/epic-kitchens-100-annotations) |

## 版本

### EPIC-KITCHENS-55

| 字段 | 内容 |
| --- | --- |
| 年份 | 2018 |
| 已发布数据 | 第一视角 RGB / 音频；抽取帧；光流 |
| 监督信号 | 旁白；动作片段；动词 / 名词类别；抽样物体框 |
| 规模 | 55 小时；32 名参与者 |

### EPIC-KITCHENS-100

| 字段 | 内容 |
| --- | --- |
| 年份 | 2020 |
| 已发布数据 | 扩展 RGB / 音频、抽取帧、光流与 GoPro 元数据 |
| 监督信号 | 扩展旁白与动作标签；97 个动词、300 个名词、4,053 个动作类别 |
| 规模 | 100 小时；700 段视频；89,977 个动作片段；37 名参与者 |

### 官方衍生版本

| 版本 | 已发布内容 | 监督信号 | 规模 |
| --- | --- | --- | --- |
| VISOR | EK-100 子集 RGB 与分割资源 | 手 / 活动物体分割与手物关系 | 36 小时；272K 人工掩码；9.9M 插值掩码 |
| EPIC-Sounds | 音频关联标注 | 音频事件区间与类别 | 117.5K 个音频事件片段 |
| EPIC Fields | 相机标定、轨迹与重建资源 | 相机内参 / 位姿与场景几何 | 671 段视频中的 18.7M 个注册帧 |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 自然环境 |
| 场景 | 家庭厨房 |
| 采集设备 | EPIC-KITCHENS-55 使用 GoPro Hero 5；后续版本沿用穿戴式 GoPro 采集 |
| 相机设置 | 人类第一视角：头戴式、移动、单目 RGB |
| 实际采集数据 | 第一视角 RGB 与相机音频；扩展版本保留 GoPro 陀螺仪和加速度计元数据 |
| 已发布数据 | RGB；音频；部分 IMU；抽取帧与光流；家族扩展数据 |

## 监督信号与数据构建

- 旁白 ← 参与者口述 + 转写。
- 动作 ← 人工标注。
- 类别 ← 语言解析 + 人工归类。
- 掩码 ← 人工关键帧 + 模型插值。
- 相机位姿 ← EPIC Fields。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 100 小时；700 段视频；89,977 个动作片段；2,000 万帧；4,053 个动作类别 |
| 开放与获取 | 公开（非商业使用）：数据、标注与代码；[官方入口](https://epic-kitchens.github.io/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| VITRA-VLA | 决策 / 动作 | 预训练 | 仅使用 EPIC-KITCHENS 原始 RGB；VITRA 生成语言与 3D 手部 / 相机动作，共 154,464 个片段 | [VITRA 论文](https://arxiv.org/abs/2510.21571)；[官方仓库](https://github.com/microsoft/VITRA) |
| EgoSteer | 决策 / 动作 | 预训练 | VITRA 筛选的 EPIC-KITCHENS 片段，经处理得到 RGB-D、手部动作、相机参数与语言；保留 49 小时 / 26,454 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| RU-LSTM | 预测 / 世界建模 | 训练 + 评测 | 观察动作发生前的 RGB、光流与物体特征，预测下一项动词、名词和动作 | [RU-LSTM 论文](https://arxiv.org/abs/1905.09035)；[官方挑战页](https://epic-kitchens.github.io/) |
| EgoVLP | 表征学习 | 微调 + 评测 | 在 Ego4D 上预训练后，使用 EPIC-KITCHENS-100 视频—文本对进行多实例检索微调与评测 | [EgoVLP EPIC-KITCHENS 报告](https://arxiv.org/abs/2207.01334) |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 74,788 个片段经筛选和手部重建，得到 32.3 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- 论文： [ECCV 2018](https://arxiv.org/abs/1804.02748)；[TPAMI 数据采集论文](https://arxiv.org/abs/2005.00343)；[EK-100 IJCV 论文](https://arxiv.org/abs/2006.13256)
- 项目页： [EPIC-KITCHENS](https://epic-kitchens.github.io/)
- 官方仓库： [EPIC-KITCHENS GitHub 组织](https://github.com/epic-kitchens)；[EK-100 标注](https://github.com/epic-kitchens/epic-kitchens-100-annotations)；[下载工具](https://github.com/epic-kitchens/epic-kitchens-download-scripts)
- 数据页： [EK-100 Data.Bris](https://data.bris.ac.uk/data/dataset/2g1n6qdydwa9u22shpxqzp0t8m)
- 文档： [EK-55 标注与视频说明](https://github.com/epic-kitchens/epic-kitchens-55-annotations)；[VISOR](https://epic-kitchens.github.io/VISOR/site)；[EPIC-Sounds](https://github.com/epic-kitchens/epic-sounds-annotations)；[EPIC Fields](https://arxiv.org/abs/2306.08731)
