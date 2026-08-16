# Awesome Ego-Centric Datasets

面向具身智能的人类第一视角数据集目录，重点比较数据采集、公开内容、监督来源、数据规模与获取方式。

当前收录 31 个数据集条目；同一数据集家族在总表中合并展示，版本差异见对应卡片。

收录边界：条目需包含可独立使用的人类第一视角数据，或在公开数据构成中明确使用此类数据构建机器人学习监督；不收录仅含机器人观测 / 动作的数据集。若聚合或转换条目并非全部样本都是第一视角，会在“相机设置”和对应卡片中明确说明。

## 数据角色

| 总表简称 | 含义 |
| --- | --- |
| 原始 | 直接发布由人类佩戴式相机采集的视频或其他原始传感器流；即使同时提供标注，也可归入此类。 |
| 标注 | 发布第一视角素材上的位姿、动作、物体、语言或几何等标注 / 重建结果；原始媒体可能随条目发布，也可能需从源数据集获取。 |
| 对齐 | 将人类视频或运动重建、重定向或转换为机器人可学习的状态、轨迹、动作或观测；该标签不表示源视频全部是第一视角。 |
| 混合 | 同一条目同时包含人类示范与机器人观测 / 动作；不单独收录仅含机器人数据的条目。 |

同一条目可以同时承担多个数据角色。角色描述条目的公开内容，不表示每个样本都同时具备全部属性；判断是否为“纯第一视角”时，应结合“相机设置”和对应卡片中的范围说明。

## 常见监督来源

| 来源 | 常见监督信号 | 说明 |
| --- | --- | --- |
| 传感器 / 设备原生 | IMU、眼动、动捕、深度、机器人状态 | 由采集设备或外部传感系统直接记录。 |
| 标定 / 几何 / SLAM | 相机位姿、深度、点云、3D 重建 | 由多视角几何、里程计、SLAM 或扫描配准计算。 |
| 人工标注 | 旁白、动作、框、分割、关键帧、任务层级 | 由标注员观察数据后直接创建或修正。 |
| 模型辅助 / 伪标签 | 手部位姿、物体位姿、深度、分割、语言 | 由检测器、姿态模型、VLM 或 LLM 生成，可结合人工复核。 |
| 重建 / 对齐 | 手部 / 物体轨迹、伪动作、机器人轨迹 / 动作 | 将人类第一视角视频转换为可学习状态，或进一步映射到机器人本体。 |

总表使用“监督信号 ← 来源 / 生成方式”表示监督信号的来源。

## 数据集总览

为保证 GitHub 页面可读性，总表使用角色简称，并只保留核心比较字段；采集设备、已发布模态、监督来源和下游使用细节见对应卡片及下表。

| 数据集 | 年份 | 数据角色 | 场景 / 视角 | 数据规模 / 任务 | 开放与获取 |
| --- | ---: | --- | --- | --- | --- |
| [Egocentric-10K / 100K 数据集家族](cards/egocentric-10k-100k.md) | 2025 | 原始 + 标注 | 自然环境 — 工厂与人工作业现场；人类第一视角：头戴式、移动、单目 RGB | 10K：10,000 小时 / 192,900 个片段；100K：100,405 小时 / 2,010,759 个片段 | 受限访问（Apache-2.0）；评测集公开；[官方入口](https://huggingface.co/datasets/builddotai/Egocentric-10K) |
| [Xperience-10M](cards/xperience-10m.md) | 2026 | 原始 + 标注 | 真实环境 — 多场景人类活动；人类第一视角：身体佩戴、移动；4 个鱼眼相机，其中一对组成校正双目 | 10,000 小时；1,000 万个交互片段；28.8 亿 RGB 帧；35 万个物体 | 受限访问（非商业使用）；公开样例与工具包；[官方入口](https://huggingface.co/datasets/ropedia-ai/xperience-10m) |
| [Ego4D](cards/ego4d.md) | 2021 | 原始 + 标注 | 自然与设计采集混合 — 家庭、户外、工作、休闲与社交；人类第一视角：头戴式、移动；含同步多第一视角子集 | 3,670 小时；74 个地点；9 个国家；5 类基准任务 | 受限访问：数据、标注与代码；[官方入口](https://ego4d-data.org/) |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | 2018 | 原始 + 标注 | 自然环境 — 家庭厨房；人类第一视角：头戴式、移动、单目 RGB | 100 小时；700 段视频；89,977 个动作片段；2,000 万帧；4,053 个动作类别 | 公开（非商业使用）：数据、标注与代码；[官方入口](https://epic-kitchens.github.io/) |
| [HD-EPIC](cards/hd-epic.md) | 2025 | 原始 + 标注 | 自然环境 — 家庭厨房；人类第一视角：头戴式 Project Aria、移动 | 41.3 小时；156 段视频；446 万帧；59,454 个动作；69 个食谱；约 2.6 万条 VQA 问题 | 公开：数据、标注与下载工具；[官方入口](https://hd-epic.github.io/site/) |
| [EgoExoLearn](cards/egoexolearn.md) | 2024 | 原始 + 标注 | 混合采集 — 厨房与专业实验室；人类第一视角：头戴式、移动；第三视角：非同步视频 | 120 小时（第一视角 96.5 小时 + 第三视角 23.5 小时）；747 段视频；约 7.8 万个细粒度片段；8 项流程任务 | 公开：数据、标注、特征与代码；[官方入口](https://egoexolearn.github.io/) |
| [ENIGMA-51](cards/enigma-51.md) | 2024 | 原始 + 标注 | 受控真实环境 — 工业实验室 / 电气板维修；人类第一视角：头戴式、移动、单目 RGB | 22 小时；51 段视频；19 名参与者；14,036 次交互；2 套维修流程 | 公开：数据、标注、衍生标签与代码；[官方入口](https://fpv-iplab.github.io/ENIGMA-51/) |
| [MECCANO 数据集家族](cards/meccano.md) | 2021 / 2023 | 原始 + 标注 | 受控真实环境 — 工业式桌面玩具组装；人类第一视角：头戴式、移动、RGB-D；头显集成眼动 | 20 段视频；8,857 个动作片段；20 名参与者；1 项组装任务；61 个动作类别 | 公开：数据、标注与代码；[官方入口](https://iplab.dmi.unict.it/legacy/MECCANO/) |
| [HoloAssist](cards/holoassist.md) | 2023 | 标注 | 受控真实环境 — 工作间、办公室、家庭与专业实验室；人类第一视角：HoloLens 2 头显、移动、RGB-D | 当前项目页口径 169 小时（ICCV 2023 论文口径 166 小时）；2,221 个会话；222 名参与者；350 对讲解者—执行者组合；20 项任务 | 公开：数据、标注与代码；[官方入口](https://holoassist.github.io/) |
| [Ego-Exo4D](cards/ego-exo4d.md) | 2023 | 标注 | 受控真实环境 — 体育、音乐、舞蹈、烹饪、维修与健康活动；人类第一视角：头戴式、移动；第三视角：多台固定相机 | 总视频 1,286.30 小时，其中第一视角 221.26 小时；5,035 次采集；8 类活动 | 受限访问：数据、标注与代码；[官方入口](https://ego-exo4d-data.org/) |
| [TACO](cards/taco.md) | 2024 | 标注 | 实验室 — 桌面工具使用；人类第一视角：头戴式 RGB-D、移动；第三视角：12 台固定 RGB 相机 | V1：2,317 个序列，其中 2,212 个含完整第一视角数据；151 个动作三元组；15 类动作 | 公开：数据、标注与工具包（CC BY 4.0）；[官方入口](https://www.dropbox.com/scl/fo/8w7xir110nbcnq8uo1845/AOaHUxGEcR0sWvfmZRQQk9g?rlkey=xnhajvn71ua5i23w75la1nidx&st=9t8ofde7&dl=0) |
| [HOI4D](cards/hoi4d.md) | 2022 | 标注 | 受控真实环境 — 室内家居、桌面与家具交互；人类第一视角：头戴式、移动、RGB-D | 4,000 个序列；240 万个传感器帧；54 项任务 | 部分公开：数据、标注与代码（CC BY-NC 4.0）；[官方入口](https://hoi4d.github.io/#data-resources) |
| [HOT3D](cards/hot3d.md) | 2025 | 标注 | 实验室 — 检查、厨房、办公室与客厅；人类第一视角：Aria / Quest 多相机头显、移动；外部动捕相机固定 | 833 分钟；425 段记录；150 万个多视角帧；370 万余张图像；4 类场景 | 受限访问：数据、标注与工具包；[官方入口](https://facebookresearch.github.io/hot3d/) |
| [SHOW3D](cards/show3d.md) | 2026 | 标注 | 自然环境 — 室内外多场景；人类第一视角：2 个头显相机、移动；第三视角：背负式采集架上的 8 个移动相机 | 20 小时；2,137 段记录；428 万个多视角帧；4,250 万张图像 | 公开：数据、标注与文档（CC BY-NC 4.0）；[官方入口](https://show3d-dataset.github.io/) |
| [H2O](cards/h2o.md) | 2021 | 标注 | 受控真实环境 — 大厅、办公室与厨房；人类第一视角：1 台头戴式 RGB-D 相机、移动；第三视角：4 台固定 RGB-D 相机 | 571,645 个五视角 RGB-D 帧；4 名参与者；36 个动作类别 | 公开：数据、标注、下载工具与查看工具（CC BY-NC 4.0）；[官方入口](https://doi.org/10.3929/ethz-b-000685070) |
| [ARCTIC](cards/arctic.md) | 2023 | 标注 | 实验室 — 动捕棚 / 关节物体交互；人类第一视角：1 台佩戴式 RGB 相机、移动；第三视角：8 台固定 RGB 相机 | 339 个序列；210 万张图像；10 名参与者；2 类采集意图 | 受限访问：数据、标注与代码；[官方入口](https://arctic.is.tue.mpg.de/) |
| [OakInk2](cards/oakink2.md) | 2024 | 标注 | 实验室 — 复杂日常任务；人类第一视角：1 台佩戴式 RGB 相机、移动；第三视角：3 台固定 RGB 相机 | 627 个序列；401 万张图像；9 名参与者 | 预览发布：数据、标注与工具包；[官方入口](https://oakink.net/v2) |
| [Assembly101](cards/assembly101.md) | 2022 | 标注 | 实验室 — 桌面玩具组装；人类第一视角：4 台头显相机、移动；第三视角：8 台固定 RGB 相机 | 513 视角小时，其中第一视角 167 小时；362 段记录；4,321 段视频；53 名参与者；101 个玩具目标；1,380 个细粒度 / 202 个粗粒度动作类别 | 公开：数据、标注、特征与代码（CC BY-NC 4.0）；[官方入口](https://assembly-101.github.io/) |
| [EgoPAT3D 数据集家族](cards/egopat3d.md) | 2022 / 2024 | 标注 | 受控真实环境 — 厨房、卧室与浴室；人类第一视角：头戴 / 头盔式、移动、RGB-D | v1：10 小时、150 段记录、15K 个动作；v2：9,579 个片段、11 名参与者；DT：11,141 个样本；动作类型包括到达、抓取、移动与放置 | 公开：数据、标注与代码；[官方入口](https://ai4ce.github.io/EgoPAT3D/) |
| [Nymeria 数据集家族](cards/nymeria.md) | 2024 / 2026 | 标注 | 自然环境 — 家庭、办公室、校园、室内与户外；人类第一视角：头戴式；另有腕载相机与移动观察相机 | 300 小时；当前发布 1,100 个序列；264 名参与者；50 个地点；20 类场景 | 受限访问：数据、标注与工具包（CC BY-NC 4.0）；[官方入口](https://www.projectaria.com/datasets/nymeria/) |
| [Aria Digital Twin (ADT)](cards/aria-digital-twin.md) | 2023 | 标注 | 实验室 / 受控真实环境 — 数字化公寓与办公室；真实采集：头戴式人类第一视角、移动，固定动捕系统；生成视角：数字孪生渲染 RGB / 深度 | V2：8.13 小时、236 个设备序列；8 项设计活动 | 受限访问：数据、标签、物体模型与工具包；[官方入口](https://www.projectaria.com/datasets/adt/) |
| [First-Person Hand Action Benchmark (FPHA)](cards/fpha.md) | 2018 | 标注 | 受控真实环境 — 厨房、办公室与社交场景；人类第一视角：肩载式 RGB-D 相机、移动 | 1,175 段视频；105,459 个 RGB-D 帧；6 名参与者；45 个动作类别 | 受限访问：数据、标注与示例代码；[官方入口](https://guiggh.github.io/publications/first-person-hands/) |
| [Open-AoE](cards/open-aoe.md) | 2026 | 原始 + 标注 + 对齐 | 自然环境 — 厨房、桌面、办公室与工作间等日常环境；人类第一视角：穿戴式手机、移动、单目 RGB | 完整版本约 2,000 小时；500 余名贡献者；400 余个场景；8,000 余项任务 | 截至 2026-08-12，nano / tiny 已发布，full 版本已上传约 694 小时且仍在分批上传；处理、重定向与训练代码公开；[官方入口](https://huggingface.co/datasets/inclusionAI/OpenAoE-2000h) |
| [VITRA-1M](cards/vitra-1m.md) | 2025 | 对齐 | 取决于聚合源数据 — 烹饪、清洁、施工、维修与手工制作；视角取决于源数据：主要为穿戴式 / 移动第一视角；另含非第一视角 SSV2 视频 | 1,222,918 个片段；2,600 万帧 | 公开：处理后标注与代码（MIT）；原始视频沿用源数据访问条款；[官方入口](https://microsoft.github.io/VITRA/) |
| [EgoScalerV2](cards/egoscaler-v2.md) | 2025 | 对齐 | 取决于聚合源数据 — Ego4D、Ego-Exo4D、HD-EPIC 与 Nymeria 日常活动；人类第一视角取决于源数据，主要为头戴移动视角 | 45,157 个片段；1,409,418 帧；30,214 条任务文本 | 公开处理数据（Apache-2.0）；[官方入口](https://biscue5.github.io/egovla-project-page/) |
| [EgoVerse](cards/egoverse.md) | 2026 | 原始 + 标注 + 对齐 | 混合采集 — 多实验室操作与工业活动；人类第一视角：头戴 / 移动；传感器配置随来源而异 | 1,362 小时；约 8 万个片段；1,965 项任务；2,087 名示范者 | 公开：数据及处理 / 训练代码；[官方入口](https://egoverse.ai/) |
| [EgoDex](cards/egodex.md) | 2025 | 原始 + 标注 + 对齐 | 受控真实环境 — 家庭桌面操作；人类第一视角：Apple Vision Pro 头显、移动、单目 RGB | 829 小时；338,000 个片段；9,000 万帧；194 项任务 | 公开：数据、标注与示例代码；[官方入口](https://machinelearning.apple.com/research/egodex-learning-dexterous-manipulation) |
| [OpenEgo](cards/openego.md) | 2025 | 标注 | 取决于六个聚合源数据集 — 厨房、组装与室内日常操作；600 余个环境；以人类佩戴式第一视角为主；部分源数据另含多视角或外部传感系统 | 1,107 小时；1.196 亿帧；344,500 段记录；290 项操作任务；600 余个环境 | 代码与当前数据下载公开；代码为 MIT，数据沿用六个源数据集各自许可证，部分底层视频需从官方源获取；[官方入口](https://www.openegocentric.com/) |
| [RoboWheel / HORA](cards/robowheel-hora.md) | 2025 | 对齐 | 实验室、源数据与仿真混合 — 家庭 / 桌面操作；源人类 HOI 视频视角不固定：HORA 自采部分为最多 11 个同步 RGB / RGB-D 视角，公开子集还包含第三视角 HOI 与机器人数据，并非全部第一视角；生成视角为机器人腕部与第三视角 RGB | 约 15 万条轨迹；HORA-Mocap 含 20 项任务 | 分阶段发布：数据与工具包（Apache-2.0）；[官方入口](https://zhangyuhong01.github.io/Robowheel/) |
| [EgoMimic](cards/egomimic.md) | 2024 | 原始 + 标注 + 对齐 + 混合 | 受控真实环境 — 室内桌面 / 家庭任务；人类第一视角：头戴式、移动；机器人视角：固定躯干相机 + 移动腕部相机 | 人类数据 4 小时 + 机器人数据 12 小时；2,150 个人类示范 + 1,000 个机器人示范；3 项任务 | 公开：处理数据、标签与代码；[官方入口](https://egomimic.github.io/) |
| [UniHand-2.0](cards/unihand-2-0.md) | 2026 | 标注 + 对齐 + 混合 | 取决于真实、仿真及聚合源数据 — 家庭、烹饪、工业、桌面机器人、仿真与 VLM 场景；视角取决于源数据：人类头戴移动第一视角，以及机器人第一视角 / 腕部 / 第三视角 | 训练配方：35K+ 小时；400M+ 样本；120B+ token；其中 16K 小时人类、14K 小时机器人、5K 等效小时 VLM 数据 | 公开预览子集与训练 / 数据准备代码；预览不等同完整训练语料；[官方入口](https://research.beingbeyond.com/being-h05) |

## 下游具身智能使用

每行表示一条已经由方法论文、项目页或官方代码确认的 Dataset → Method 使用关系。方法名称链接到直接证据，数据集名称链接到详细卡片。

| 数据集 | 方法 | 方法类别 | 数据使用方式与作用 | 使用阶段 |
| --- | --- | --- | --- | --- |
| [Egocentric-10K / 100K 数据集家族](cards/egocentric-10k-100k.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | EgoSmith 处理降采样原始视频；最终保留 Egocentric-10K 的 288 小时 / 194,915 个片段，以及 Egocentric-100K 的 8,049 小时 / 1,795,731 个片段，并生成手部、深度、相机与语言监督 | 预训练 |
| [Xperience-10M](cards/xperience-10m.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 99,027 个片段经筛选、3D 手部重建与动作参数化，得到 435.7 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [Ego4D](cards/ego4d.md) | [VITRA-VLA](https://arxiv.org/abs/2510.21571) | 决策 / 动作 | 仅使用 Ego4D 原始 RGB；VITRA 生成原子语言与 3D 手部 / 相机动作，两个子集共 948,683 个片段 | 预训练 |
| [Ego4D](cards/ego4d.md) | [π0（EgoScalerV2）](https://arxiv.org/abs/2509.21986) | 决策 / 动作 | Ego4D RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | 预训练 |
| [Ego4D](cards/ego4d.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | VITRA 筛选的 Ego4D 片段，经处理得到 RGB-D、手部动作、相机参数与语言；保留 138 小时 / 74,505 个片段 | 预训练 |
| [Ego4D](cards/ego4d.md) | [R3M](https://arxiv.org/abs/2203.12601) | 表征学习 | Ego4D 视频与语言用于时间对比、视频—语言对齐预训练；所得视觉表示作为机器人策略的冻结感知模块 | 预训练 |
| [Ego4D](cards/ego4d.md) | [EgoVLP](https://arxiv.org/abs/2206.01670) | 表征学习 | 从 Ego4D 构建 380 万视频—文本对进行预训练，并在 Ego4D 的语言查询、时刻查询和物体状态变化任务上微调与评测 | 预训练 + 微调 + 评测 |
| [Ego4D](cards/ego4d.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 948,683 个片段经筛选和手部重建，得到 216.6 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | [VITRA-VLA](https://arxiv.org/abs/2510.21571) | 决策 / 动作 | 仅使用 EPIC-KITCHENS 原始 RGB；VITRA 生成语言与 3D 手部 / 相机动作，共 154,464 个片段 | 预训练 |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | VITRA 筛选的 EPIC-KITCHENS 片段，经处理得到 RGB-D、手部动作、相机参数与语言；保留 49 小时 / 26,454 个片段 | 预训练 |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | [RU-LSTM](https://arxiv.org/abs/1905.09035) | 预测 / 世界建模 | 观察动作发生前的 RGB、光流与物体特征，预测下一项动词、名词和动作 | 训练 + 评测 |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | [EgoVLP](https://arxiv.org/abs/2207.01334) | 表征学习 | 在 Ego4D 上预训练后，使用 EPIC-KITCHENS-100 视频—文本对进行多实例检索微调与评测 | 微调 + 评测 |
| [EPIC-KITCHENS 数据集家族](cards/epic-kitchens.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 74,788 个片段经筛选和手部重建，得到 32.3 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [HD-EPIC](cards/hd-epic.md) | [π0（EgoScalerV2）](https://arxiv.org/abs/2509.21986) | 决策 / 动作 | HD-EPIC RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | 预训练 |
| [EgoExoLearn](cards/egoexolearn.md) | [TimeSformer–CLIP cross-view association baseline](https://arxiv.org/abs/2403.16182) | 表征学习 | 异步第一 / 第三视角视频与描述文本用于学习跨视角视频—文本对应关系 | 训练 + 评测 |
| [EgoExoLearn](cards/egoexolearn.md) | [CLIP + TA3N anticipation / planning baseline](https://arxiv.org/abs/2403.16182) | 预测 / 世界建模 | 第一 / 第三视角视频、动作标签及可选眼动用于预测下一动作和后续 8 个流程步骤 | 训练 + 评测 |
| [ENIGMA-51](cards/enigma-51.md) | [egoism-hoi](https://github.com/fpv-iplab/ENIGMA-51#egocentric-human-object-interaction-detection) | 具身感知 | 第一视角帧、手部和活动物体标注用于检测当前手—物交互 | 训练 + 评测 |
| [ENIGMA-51](cards/enigma-51.md) | [StillFast](https://github.com/fpv-iplab/ENIGMA-51#short-term-object-interaction-anticipation) | 预测 / 世界建模 | 第一视角视频与交互标注用于短期物体交互预判 | 训练 + 评测 |
| [MECCANO 数据集家族](cards/meccano.md) | [SlowFast EHOI baseline](https://github.com/fpv-iplab/MECCANO#3-egocentric-human-object-interaction-ehoi-detection) | 具身感知 | RGB 或深度视频、动词及活动物体标注用于第一视角手—物交互检测 | 训练 + 评测 |
| [MECCANO 数据集家族](cards/meccano.md) | [RU-LSTM](https://github.com/fpv-iplab/MECCANO#4-action-anticipation) | 预测 / 世界建模 | 物体、眼动和手部特征用于预测下一项操作动作 | 训练 + 评测 |
| [HoloAssist](cards/holoassist.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 第一视角片段经 EgoSmith 统一为训练样本；保留 11.5 小时 / 11,426 个片段 | 预训练 |
| [HoloAssist](cards/holoassist.md) | [TimeSformer baseline](https://arxiv.org/abs/2309.17024) | 预测 / 世界建模 | 第一视角视频及可选传感器用于下一动作、错误和干预类型预测 | 训练 + 评测 |
| [HoloAssist](cards/holoassist.md) | [Seq2Seq hand-forecasting baseline](https://openaccess.thecvf.com/content/ICCV2023/supplemental/Wang_HoloAssist_an_Egocentric_ICCV_2023_supplemental.pdf) | 预测 / 世界建模 | 历史 3D 手部关节序列用于预测未来 1.5 秒手部运动 | 训练 + 评测 |
| [Ego-Exo4D](cards/ego-exo4d.md) | [VITRA-VLA](https://arxiv.org/abs/2510.21571) | 决策 / 动作 | 第一视角 RGB 经处理生成原子语言与 3D 手部 / 相机动作，共 67,053 个片段 | 预训练 |
| [Ego-Exo4D](cards/ego-exo4d.md) | [π0（EgoScalerV2）](https://arxiv.org/abs/2509.21986) | 决策 / 动作 | 第一视角 RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | 预训练 |
| [Ego-Exo4D](cards/ego-exo4d.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 41,414 个第一视角片段经筛选和手部重建，得到 10.3 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [TACO](cards/taco.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 使用原生 RGB-D、手部 / 相机标注；EgoSmith 补充语言并统一格式；保留 3.0 小时 / 1,558 个片段 | 预训练 |
| [TACO](cards/taco.md) | [CAHMP](https://arxiv.org/abs/2401.08399) | 预测 / 世界建模 | 物体点云与连续 10 帧双手 / 双物体位姿用于预测后续 10 帧运动 | 训练 + 评测 |
| [HOI4D](cards/hoi4d.md) | [P4Transformer baseline](https://arxiv.org/abs/2203.01577) | 具身感知 | 4D 点云与逐点语义标签用于时空点云语义分割 | 训练 + 评测 |
| [HOI4D](cards/hoi4d.md) | [GAIL dexterous-manipulation baseline](https://arxiv.org/html/2203.01577#Sx12) | 决策 / 动作 | 人手与物体位姿经重定向生成 12 条 Adroit Hand 状态—动作示范，用于灵巧手拾取策略学习 | 训练 + 评测 |
| [HOI4D](cards/hoi4d.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 2,966 个片段经筛选和手部重建，得到 7.2 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [HOT3D](cards/hot3d.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 第一视角片段经 EgoSmith 统一为训练样本；保留 4.5 小时 / 1,105 个片段 | 预训练 |
| [HOT3D](cards/hot3d.md) | [UmeTrack](https://arxiv.org/abs/2411.19167) | 具身感知 | 单视角和多视角头显图像用于 3D 手部位姿跟踪评测 | 评测 |
| [HOT3D](cards/hot3d.md) | [FoundPose](https://arxiv.org/abs/2411.19167) | 具身感知 | 单视角与多视角图像、物体 CAD 模型用于 6DoF 物体位姿估计评测 | 评测 |
| [SHOW3D](cards/show3d.md) | [InterField](https://arxiv.org/abs/2603.28760) | 具身感知 | 手部 / 物体网格与视频用于逐顶点手—物距离场估计及跨数据集评测 | 训练 + 评测 |
| [SHOW3D](cards/show3d.md) | [Text-conditioned 6DoF pose forecasting baseline](https://arxiv.org/abs/2603.28760) | 预测 / 世界建模 | 历史物体位姿与场景描述用于预测 30 / 60 帧后的物体 6DoF 位姿 | 训练 + 评测 |
| [H2O](cards/h2o.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 使用原生 RGB-D、双手 / 相机标注；EgoSmith 补充语言并统一格式；保留 1.0 小时 / 935 个片段 | 预训练 |
| [H2O](cards/h2o.md) | [USST](https://arxiv.org/abs/2307.08243) | 预测 / 世界建模 | 第一视角 RGB 与历史手部运动用于预测未来 2D / 3D 手部轨迹 | 训练 + 评测 |
| [ARCTIC](cards/arctic.md) | [ArcticNet](https://arxiv.org/abs/2204.13662) | 具身感知 | RGB 视频与双手 / 关节物体监督用于重建连续的 3D 手—物运动 | 训练 + 评测 |
| [ARCTIC](cards/arctic.md) | [InterField](https://arxiv.org/abs/2204.13662) | 具身感知 | RGB 视频与手—物网格用于估计逐顶点交互距离场 | 训练 + 评测 |
| [OakInk2](cards/oakink2.md) | [TaMF / Complex Task Completion](https://openaccess.thecvf.com/content/CVPR2024/html/Zhan_OAKINK2_A_Dataset_of_Bimanual_Hands-Object_Manipulation_in_Complex_Task_CVPR_2024_paper.html) | 预测 / 世界建模 | 原子 / 复杂任务层级、物体轨迹与双手运动 | 训练 + 评测 |
| [OakInk2](cards/oakink2.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | EgoSmith 从 OakInk2 保留 1.7 小时 / 891 个片段，并生成深度监督 | 预训练 |
| [Assembly101](cards/assembly101.md) | [TempAgg](https://arxiv.org/abs/2203.14712) | 预测 / 世界建模 | 多视角视频特征与动作 / 错误标签用于下一动作预判和装配错误早期预测 | 训练 + 评测 |
| [EgoPAT3D 数据集家族](cards/egopat3d.md) | [EgoPAT3D LSTM baseline](https://ai4ce.github.io/EgoPAT3D/about.html) | 预测 / 世界建模 | RGB-D、IMU、历史手部位置与视觉里程计用于连续预测 3D 操作目标 | 训练 + 评测 |
| [EgoPAT3D 数据集家族](cards/egopat3d.md) | [USST](https://arxiv.org/abs/2307.08243) | 预测 / 世界建模 | 第一视角 RGB 与历史手部运动用于预测未来 2D / 3D 手部轨迹 | 训练 + 评测 |
| [EgoPAT3D 数据集家族](cards/egopat3d.md) | [EgoPAT3Dv2 baseline](https://ai4ce.github.io/EgoPAT3Dv2/) | 预测 / 世界建模 | RGB 与 MediaPipe 手部关键点用于预测 3D 操作目标，并在真实协作机器人任务中验证 | 训练 + 评测 |
| [Nymeria 数据集家族](cards/nymeria.md) | [π0（EgoScalerV2）](https://arxiv.org/abs/2509.21986) | 决策 / 动作 | Nymeria RGB 片段转换为任务文本与重建的 6DoF 物体状态 / 动作轨迹 | 预训练 |
| [Nymeria 数据集家族](cards/nymeria.md) | [HMD²](https://hmdsquared.github.io/) | 预测 / 世界建模 | Project Aria 图像、头部运动与场景点云用于在线生成佩戴者全身运动 | 训练 + 评测 |
| [Aria Digital Twin (ADT)](cards/aria-digital-twin.md) | [ViT-Det](https://arxiv.org/abs/2306.06362) | 具身感知 | 校正后的 Aria RGB 与 2D 框 / 实例掩码用于第一视角物体检测和分割评测 | 评测 |
| [Aria Digital Twin (ADT)](cards/aria-digital-twin.md) | [Cube R-CNN](https://arxiv.org/abs/2306.06362) | 具身感知 | 校正后的 Aria RGB 与 3D 物体框用于单目 3D 物体检测评测 | 评测 |
| [First-Person Hand Action Benchmark (FPHA)](cards/fpha.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 第一视角片段经 EgoSmith 统一为训练样本；保留 0.5 小时 / 578 个片段 | 预训练 |
| [Open-AoE](cards/open-aoe.md) | [VITRA Training-Ready recipe](https://github.com/ant-research/Open-AoE) | 决策 / 动作 | 将 Open-AoE 的 RGB、手部 / 相机运动和原子动作转换为 VITRA 所需状态—动作语义，并提供训练启动配置 | 训练 |
| [Open-AoE](cards/open-aoe.md) | [DreamZero Training-Ready recipe](https://github.com/ant-research/Open-AoE) | 预测 / 世界建模 | 将 Open-AoE 片段转换为视频—动作世界模型所需格式，并提供训练配方 | 训练 |
| [VITRA-1M](cards/vitra-1m.md) | [VITRA-VLA](https://arxiv.org/abs/2510.21571) | 决策 / 动作 | RGB 观测、语言指令与重建的 3D 手部状态 / 动作序列 | 预训练 |
| [EgoScalerV2](cards/egoscaler-v2.md) | [π0（EgoScalerV2）](https://arxiv.org/abs/2509.21986) | 决策 / 动作 | 第一视角 RGB、任务文本与重建的物体状态 / 动作轨迹 | 预训练 |
| [EgoVerse](cards/egoverse.md) | [EgoVerse cross-embodiment policy](https://arxiv.org/abs/2604.07607) | 决策 / 动作 | 第一视角 RGB、相机坐标系中的未来手部轨迹与任务语言，和机器人轨迹联合训练 | 训练 + 评测 |
| [EgoVerse](cards/egoverse.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 使用原生手部 / 相机标注；EgoSmith 补充深度和语言并统一格式；保留 690 小时 / 35,175 个片段 | 预训练 |
| [EgoDex](cards/egodex.md) | [EgoSteer](https://arxiv.org/abs/2607.09701) | 决策 / 动作 | 使用 EgoDex 原生 RGB、手部 / 相机位姿与语言；EgoSmith 补充深度并统一格式；保留 370 小时 / 147,588 个片段 | 预训练 |
| [EgoDex](cards/egodex.md) | [ACE-Ego-0](https://arxiv.org/abs/2606.17200) | 决策 / 动作 | 327,317 个片段经筛选和动作统一，得到 776.8 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | 预训练 |
| [OpenEgo](cards/openego.md) | [Language-conditioned hand-trajectory prediction baseline](https://arxiv.org/abs/2509.05513) | 预测 / 世界建模 | 语言动作原语与历史 3D 双手关节用于预测未来 0.5–4.0 秒的灵巧手轨迹 | 训练 + 评测 |
| [RoboWheel / HORA](cards/robowheel-hora.md) | [ACT](https://arxiv.org/abs/2512.02729) | 决策 / 动作 | 每项任务使用 10 条 HORA 机器人观测 / 动作轨迹 | 微调 + 评测 |
| [RoboWheel / HORA](cards/robowheel-hora.md) | [Diffusion Policy](https://arxiv.org/abs/2512.02729) | 决策 / 动作 | 每项任务使用 10 条 HORA 机器人观测 / 动作轨迹 | 微调 + 评测 |
| [RoboWheel / HORA](cards/robowheel-hora.md) | [RDT](https://arxiv.org/abs/2512.02729) | 决策 / 动作 | 使用 5K 条 HORA 轨迹预训练，再按每项任务 10 条轨迹微调 | 预训练 + 微调 + 评测 |
| [RoboWheel / HORA](cards/robowheel-hora.md) | [π0](https://arxiv.org/abs/2512.02729) | 决策 / 动作 | 使用 5K 条 HORA 轨迹预训练，再按每项任务 10 条轨迹微调 | 预训练 + 微调 + 评测 |
| [RoboWheel / HORA](cards/robowheel-hora.md) | [ManipTrans](https://arxiv.org/abs/2512.02729) | 决策 / 动作 | 将 HORA 手部运动在仿真中重定向到机器人灵巧手 | 训练 |
| [EgoMimic](cards/egomimic.md) | [EgoMimic](https://arxiv.org/abs/2410.24221) | 决策 / 动作 | 人类第一视角 RGB 与 MPS 生成的 3D 手部 / 末端轨迹，和机器人 RGB、本体状态及动作联合训练 | 训练 + 评测 |
| [UniHand-2.0](cards/unihand-2-0.md) | [Being-H0.5](https://arxiv.org/abs/2601.12993) | 决策 / 动作 | 人类第一视角视频、手部运动 / 语言、多本体机器人观测 / 动作与视觉语言监督 | 预训练 |

更详细的数据构建、使用数量与证据见对应[数据集卡片](cards/)。
