# Xperience-10M

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2026 |
| 机构 | Ropedia |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 项目 / 数据 | [Xperience-10M](https://huggingface.co/datasets/ropedia-ai/xperience-10m)；[公开样例](https://huggingface.co/datasets/ropedia-ai/xperience-10m-sample) |
| 代码 | [HOMIE Toolkit](https://github.com/Ropedia/HOMIE-toolkit) |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人体 / 双手 |
| 采集条件 | 真实环境 |
| 场景 | 多场景人类活动 |
| 采集设备 | 定制同步多相机与运动感知系统 |
| 相机设置 | 人类第一视角：身体佩戴、移动；4 个鱼眼相机，其中一对组成校正双目 |
| 实际采集数据 | 4 路鱼眼 RGB、1 对双目 RGB、音频、手部 / 全身动捕与 IMU；深度和相机运动由后处理生成 |
| 已发布数据 | 六视角 RGB；音频；双目深度；点云；手部 / 身体动捕；IMU；分层英文描述 |

## 监督信号与数据构建

- 手部 / 身体位姿与接触 ← 动捕系统。
- 相机位姿 ← SLAM。
- 深度 ← 双目几何。
- 任务 / 子任务 / 动作 / 交互 / 物体描述 ← LLM / VLM 语义层。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 10,000 小时；1,000 万个交互片段；28.8 亿 RGB 帧；35 万个物体 |
| 开放与获取 | 受限访问（非商业使用）；公开样例与工具包；[官方入口](https://huggingface.co/datasets/ropedia-ai/xperience-10m) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| ACE-Ego-0 | 决策 / 动作 | 预训练 | 99,027 个片段经筛选、3D 手部重建与动作参数化，得到 435.7 小时相机坐标系伪动作，用于 VLA 人机数据联合预训练 | [ACE-Ego-0 论文](https://arxiv.org/abs/2606.17200) |

## 官方来源

- [官方数据页](https://huggingface.co/datasets/ropedia-ai/xperience-10m)
- [官方数据说明](https://ropedia.com/blog/20260316_xperience_10m)
- 样例：[Hugging Face](https://huggingface.co/datasets/ropedia-ai/xperience-10m-sample)
- 工具包：[官方仓库](https://github.com/Ropedia/HOMIE-toolkit)
