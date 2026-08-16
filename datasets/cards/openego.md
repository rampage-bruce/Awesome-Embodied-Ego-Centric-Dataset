# OpenEgo

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | The University of Texas at Dallas |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [OpenEgo: A Large-Scale Multimodal Egocentric Dataset for Dexterous Manipulation](https://arxiv.org/abs/2509.05513) |
| 项目 / 数据 | [项目页](https://www.openegocentric.com/)；[数据下载](https://utdallas.box.com/s/1fzj9gr331atfumk5on3bifzpp2idnjr) |
| 代码 | [官方仓库](https://github.com/ahadjawaid/openego) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 单手 / 双手 |
| 采集条件 | 取决于六个聚合源数据集 |
| 场景 | 厨房、组装与室内日常操作；600 余个环境 |
| 采集设备 | 沿用 CaptainCook4D、HOI4D、HoloAssist、EgoDex、HOT3D 与 HO-Cap 的设备 |
| 相机设置 | 以人类佩戴式第一视角为主；部分源数据另含多视角或外部传感系统 |
| 实际采集数据 | 不新增采集；聚合六个公开数据集的第一视角 RGB / RGB-D、手部位姿与元数据 |
| 已发布数据 | RGB 视频或源视频引用；相机坐标系 MANO-21 双手 3D 关节与可见性；相机内参；高层任务；带时间戳的动作原语与元数据 |

## 监督信号与数据构建

- 3D 手部位姿 ← 源数据标注统一到相机坐标系 MANO-21；CaptainCook4D 使用 MediaPipe 关键点 + 深度反投影补全。
- 可见性与相机参数 ← 源数据标签、内外参与坐标变换。
- 动作原语 ← 面向操作意图的自动语言标注 + 部分人工核验。
- 片段边界 / 操作物体 / 执行手 ← 带起止时间、对象和 actor 字段的细粒度标注。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 1,107 小时；1.196 亿帧；344,500 段记录；290 项操作任务；600 余个环境 |
| 开放与获取 | 代码与当前数据下载公开；代码为 MIT，数据沿用六个源数据集各自许可证，部分底层视频需从官方源获取；[官方入口](https://www.openegocentric.com/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| Language-conditioned hand-trajectory prediction baseline | 预测 / 世界建模 | 训练 + 评测 | 语言动作原语与历史 3D 双手关节用于预测未来 0.5–4.0 秒的灵巧手轨迹 | [论文](https://arxiv.org/abs/2509.05513) |

## 官方来源

- [论文](https://arxiv.org/abs/2509.05513)
- [项目页](https://www.openegocentric.com/)
- [官方仓库](https://github.com/ahadjawaid/openego)
- [数据下载](https://utdallas.box.com/s/1fzj9gr331atfumk5on3bifzpp2idnjr)
- [许可证与归属说明](https://github.com/ahadjawaid/openego/blob/main/ATTRIBUTION.md)
