# Egocentric-10K / 100K 数据集家族

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 机构 | Build AI |
| 数据角色 | 原始人类第一视角数据 + 带标注的人类第一视角数据 |
| 项目 / 数据 | [Egocentric-10K](https://huggingface.co/datasets/builddotai/Egocentric-10K); [Egocentric-100K](https://huggingface.co/datasets/builddotai/Egocentric-100K) |
| 代码 | 数据卡提供 WebDataset / Hugging Face 加载示例 |

## 版本

### Egocentric-10K

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 已发布数据 | 1920 × 1080 单目 RGB；相机内参；视频技术元数据；不含音频 |
| 监督信号 | 主视频库无附加监督标签 |
| 规模 | 10,000 小时；192,900 个片段；10.8 亿帧 |
| 获取 | Hugging Face 受限访问；Apache-2.0 |

### Egocentric-100K

| 字段 | 内容 |
| --- | --- |
| 年份 | 2025 |
| 已发布数据 | 456 × 256 单目 RGB；相机内参；视频技术元数据；不含音频 |
| 监督信号 | 主视频库无附加监督标签 |
| 规模 | 100,405 小时；2,010,759 个片段；108 亿帧 |
| 获取 | Hugging Face 受限访问；Apache-2.0 |

### 评测版本

| 版本 | 已发布数据 | 监督信号 | 生成方式 | 规模 |
| --- | --- | --- | --- | --- |
| [Egocentric-10K-Evaluation](https://huggingface.co/datasets/builddotai/Egocentric-10K-Evaluation) | 单帧图像；来源数据集名称 | 可见手部数量；是否正在主动操作物体 | Gemini-2.5-Flash 按官方提示词逐帧标注 | 30,000 帧，其中 10,000 帧来自 Egocentric-10K |
| [Egocentric-100K-Evaluation](https://huggingface.co/datasets/builddotai/Egocentric-100K-Evaluation) | 单帧图像；来源数据集名称 | 可见手部数量；是否正在主动操作物体 | Gemini-2.5-Flash 按官方提示词逐帧标注 | 30,000 帧，其中 10,000 帧来自 Egocentric-100K |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 人手 |
| 采集条件 | 自然环境 |
| 场景 | 工厂与人工作业现场 |
| 采集设备 | Build AI Gen 1 |
| 相机设置 | 人类第一视角：头戴式、移动、单目 RGB |
| 实际采集数据 | 单目 RGB 视频；逐采集者标定的相机内参；不含音频 |
| 已发布数据 | RGB 视频片段；相机内参；视频技术元数据；单帧评测集 |

## 监督信号与数据构建

- 主 10K / 100K 视频库无附加监督标签。
- 相机内参由逐采集者设备标定获得；技术元数据仅记录工厂 / 采集者 ID、视频序号、时长、分辨率、帧率、文件大小与编码格式。
- 独立评测集的手部数量与主动操作标签由 Gemini-2.5-Flash 生成。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 10K：10,000 小时 / 192,900 个片段；100K：100,405 小时 / 2,010,759 个片段 |
| 开放与获取 | 受限访问（Apache-2.0）；评测集公开；[官方入口](https://huggingface.co/datasets/builddotai/Egocentric-10K) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | EgoSmith 处理降采样原始视频；最终保留 Egocentric-10K 的 288 小时 / 194,915 个片段，以及 Egocentric-100K 的 8,049 小时 / 1,795,731 个片段，并生成手部、深度、相机与语言监督 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701)；[EgoSmith 代码](https://github.com/egosteer/egosmith) |

## 官方来源

- 数据页：[Egocentric-10K](https://huggingface.co/datasets/builddotai/Egocentric-10K)；[Egocentric-100K](https://huggingface.co/datasets/builddotai/Egocentric-100K)
- 评测集：[Egocentric-10K-Evaluation](https://huggingface.co/datasets/builddotai/Egocentric-10K-Evaluation)；[Egocentric-100K-Evaluation](https://huggingface.co/datasets/builddotai/Egocentric-100K-Evaluation)
- 使用论文：[EgoSteer](https://arxiv.org/abs/2607.09701)
- 处理代码：[EgoSmith](https://github.com/egosteer/egosmith)
