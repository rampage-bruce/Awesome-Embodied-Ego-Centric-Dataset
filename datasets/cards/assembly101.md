# Assembly101

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2022 |
| 机构 | Meta Reality Labs Research; National University of Singapore |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [Assembly101: A Large-Scale Multi-View Video Dataset for Understanding Procedural Activities](https://openaccess.thecvf.com/content/CVPR2022/html/Sener_Assembly101_A_Large-Scale_Multi-View_Video_Dataset_for_Understanding_Procedural_Activities_CVPR_2022_paper.html) |
| 项目 / 数据 | [项目页](https://assembly-101.github.io/)；Google Drive 与 Hugging Face 下载入口见官方仓库 |
| 代码 | https://github.com/assembly-101/assembly101-annotations; https://github.com/assembly-101/assembly101-download-scripts |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 实验室 |
| 场景 | 桌面玩具组装 |
| 采集设备 | 8 台固定 RGB 相机组成的桌面机架；4 相机灰度头显；SMPTE 时间码与标志点标定 |
| 相机设置 | 人类第一视角：4 台头显相机、移动；第三视角：8 台固定 RGB 相机 |
| 实际采集数据 | 8 路固定 RGB 与 4 路移动第一视角灰度视频；统一时间码与相机标定 |
| 已发布数据 | 四视角第一视角灰度视频；八视角第三视角 RGB |

## 监督信号与数据构建

- 手部位姿 ← 改进 MegATrack + 多视角几何。
- 动作、错误与技能 ← 人工标注。
- 标定 ← 基于标志点的相机标定。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 513 视角小时，其中第一视角 167 小时；362 段记录；4,321 段视频；53 名参与者；101 个玩具目标；1,380 个细粒度 / 202 个粗粒度动作类别 |
| 开放与获取 | 公开：数据、标注、特征与代码（CC BY-NC 4.0）；[官方入口](https://assembly-101.github.io/) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| TempAgg | 预测 / 世界建模 | 训练 + 评测 | 多视角视频特征与动作 / 错误标签用于下一动作预判和装配错误早期预测 | [Assembly101 论文](https://arxiv.org/abs/2203.14712)；[项目页](https://assembly-101.github.io/) |

## 官方来源

- 论文： [CVPR 2022](https://openaccess.thecvf.com/content/CVPR2022/html/Sener_Assembly101_A_Large-Scale_Multi-View_Video_Dataset_for_Understanding_Procedural_Activities_CVPR_2022_paper.html)；[arXiv](https://arxiv.org/html/2203.14712)
- 项目页： https://assembly-101.github.io/
- 官方仓库： https://github.com/assembly-101/assembly101-annotations; https://github.com/assembly-101/assembly101-download-scripts
- 数据页： [官方下载工具](https://github.com/assembly-101/assembly101-download-scripts)
- 文档： [动作标注](https://github.com/assembly-101/assembly101-annotations)；[数据包与获取方式](https://github.com/assembly-101/assembly101-download-scripts)；[AssemblyHands 工具包](https://github.com/facebookresearch/assemblyhands-toolkit)
