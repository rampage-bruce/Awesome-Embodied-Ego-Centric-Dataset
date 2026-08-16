# TACO

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2024 |
| 机构 | Tsinghua University; Shanghai Artificial Intelligence Laboratory; Shanghai Qi Zhi Institute; Beijing University of Posts and Telecommunications; Beijing Institute of Technology |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [TACO: Benchmarking Generalizable Bimanual Tool-ACtion-Object Understanding](https://openaccess.thecvf.com/content/CVPR2024/html/Liu_TACO_Benchmarking_Generalizable_Bimanual_Tool-ACtion-Object_Understanding_CVPR_2024_paper.html) |
| 项目 / 数据 | [项目页](https://taco2024.github.io/)；[V1 数据下载](https://www.dropbox.com/scl/fo/8w7xir110nbcnq8uo1845/AOaHUxGEcR0sWvfmZRQQk9g?rlkey=xnhajvn71ua5i23w75la1nidx&st=9t8ofde7&dl=0) |
| 代码 | https://github.com/leolyliu/TACO-Instructions |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 实验室 |
| 场景 | 桌面工具使用 |
| 采集设备 | 12 台 FLIR RGB 相机；NOKOV 光学动捕系统；头盔式 RealSense L515；EinScan 物体扫描仪 |
| 相机设置 | 人类第一视角：头戴式 RGB-D、移动；第三视角：12 台固定 RGB 相机 |
| 实际采集数据 | 1 路第一视角 RGB-D；12 路第三视角 RGB；物体与第一视角相机动捕标记；预扫描物体网格 |
| 已发布数据 | 第一视角 RGB-D；12 视角第三视角 RGB；物体网格 |

## 监督信号与数据构建

- 手部位姿 ← 2D 检测 + 多视角三角化 + MANO 优化。
- 相机 / 物体位姿 ← 光学动捕 + 标定。
- 掩码 ← 网格投影 + SAM / Track Anything。
- 动作三元组 ← 采集元数据。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | V1：2,317 个序列，其中 2,212 个含完整第一视角数据；151 个动作三元组；15 类动作 |
| 开放与获取 | 公开：数据、标注与工具包（CC BY 4.0）；[官方入口](https://www.dropbox.com/scl/fo/8w7xir110nbcnq8uo1845/AOaHUxGEcR0sWvfmZRQQk9g?rlkey=xnhajvn71ua5i23w75la1nidx&st=9t8ofde7&dl=0) |

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 使用原生 RGB-D、手部 / 相机标注；EgoSmith 补充语言并统一格式；保留 3.0 小时 / 1,558 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |
| CAHMP | 预测 / 世界建模 | 训练 + 评测 | 物体点云与连续 10 帧双手 / 双物体位姿用于预测后续 10 帧运动 | [TACO 论文](https://arxiv.org/abs/2401.08399) |

## 官方来源

- 论文： [CVPR 2024](https://openaccess.thecvf.com/content/CVPR2024/html/Liu_TACO_Benchmarking_Generalizable_Bimanual_Tool-ACtion-Object_Understanding_CVPR_2024_paper.html)；[补充材料](https://openaccess.thecvf.com/content/CVPR2024/supplemental/Liu_TACO_Benchmarking_Generalizable_CVPR_2024_supplemental.pdf)；[arXiv](https://arxiv.org/abs/2401.08399)
- 项目页： https://taco2024.github.io/
- 官方仓库： https://github.com/leolyliu/TACO-Instructions
- 数据页： [Version 1](https://www.dropbox.com/scl/fo/8w7xir110nbcnq8uo1845/AOaHUxGEcR0sWvfmZRQQk9g?rlkey=xnhajvn71ua5i23w75la1nidx&st=9t8ofde7&dl=0)
- 文档： [官方仓库说明](https://github.com/leolyliu/TACO-Instructions#readme)；[V1 数据清单](https://github.com/leolyliu/TACO-Instructions/tree/master/data_lists)
