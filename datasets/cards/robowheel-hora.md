# RoboWheel / HORA

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Tsinghua University; Synapath; The Chinese University of Hong Kong; The University of Hong Kong; The Hong Kong Polytechnic University |
| 数据角色 | 机器人对齐的人类数据 |
| 论文 | [RoboWheel: A Data Engine from Real-World Human Demonstrations for Cross-Embodiment Robotic Learning](https://arxiv.org/abs/2512.02729) |
| 项目 / 数据 | [项目页](https://zhangyuhong01.github.io/Robowheel/)；[HORA 数据](https://huggingface.co/datasets/HORA-DB/HORA) |
| 代码 | [RoboWheel Toolkits](https://github.com/zhangyuhong01/Robowheel-Toolkits) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 → 机器人夹爪 / 灵巧手 / 人形机器人 |
| 采集条件 | 实验室、源数据与仿真混合 |
| 场景 | 家庭 / 桌面操作 |
| 采集设备 | HORA-Mocap 使用 3 台 RealSense D455、8 台 RGB 相机与 Paxini EVT2 触觉手套；其他子集按来源配置 |
| 相机设置 | 源人类 HOI 视频视角不固定：HORA 自采部分为最多 11 个同步 RGB / RGB-D 视角，公开子集还包含第三视角 HOI 与机器人数据，并非全部第一视角；生成视角为机器人腕部与第三视角 RGB |
| 实际采集数据 | 多视角 RGB-D / RGB、手套关节、触觉力、源视频与源 HOI 标注 |
| 已发布数据 | 机器人腕部 / 第三视角 RGB；机器人状态 / 动作；物体资产；部分样本含触觉 |

> 范围说明：RoboWheel / HORA 不是纯第一视角数据集。本目录将其作为边界条目收录，是因为公开构成包含 TACO 等人类第一视角来源，并将人类 HOI 运动统一转换为机器人监督；其余来源和生成数据可为第三视角或机器人视角。

## 监督信号与数据构建

- 手部 / 物体运动 ← 按子集采用动捕、源标签或 RoboWheel 重建。
- 接触 ← 触觉传感 + 几何。
- 机器人动作 / 视角 ← 逆运动学重定向 + 仿真回放。
- 回放成功状态 ← Qwen2.5-VL。
- 任务文本 ← 自动生成流程。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 约 15 万条轨迹；HORA-Mocap 含 20 项任务 |
| 开放与获取 | 分阶段发布：数据与工具包（Apache-2.0）；[官方入口](https://zhangyuhong01.github.io/Robowheel/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| ACT | 决策 / 动作 | 微调 + 评测 | 每项任务使用 10 条 HORA 机器人观测 / 动作轨迹 | [RoboWheel 论文](https://arxiv.org/abs/2512.02729) |
| Diffusion Policy | 决策 / 动作 | 微调 + 评测 | 每项任务使用 10 条 HORA 机器人观测 / 动作轨迹 | [RoboWheel 论文](https://arxiv.org/abs/2512.02729) |
| RDT | 决策 / 动作 | 预训练 + 微调 + 评测 | 使用 5K 条 HORA 轨迹预训练，再按每项任务 10 条轨迹微调 | [RoboWheel 论文](https://arxiv.org/abs/2512.02729) |
| π0 | 决策 / 动作 | 预训练 + 微调 + 评测 | 使用 5K 条 HORA 轨迹预训练，再按每项任务 10 条轨迹微调 | [RoboWheel 论文](https://arxiv.org/abs/2512.02729) |
| ManipTrans | 决策 / 动作 | 训练 | 将 HORA 手部运动在仿真中重定向到机器人灵巧手 | [RoboWheel 论文附录 D.2](https://arxiv.org/abs/2512.02729) |

## 官方来源

- [论文](https://arxiv.org/abs/2512.02729)
- [项目页](https://zhangyuhong01.github.io/Robowheel/)
- 数据页：[HORA](https://huggingface.co/datasets/HORA-DB/HORA)
- 工具包：[官方仓库](https://github.com/zhangyuhong01/Robowheel-Toolkits)
