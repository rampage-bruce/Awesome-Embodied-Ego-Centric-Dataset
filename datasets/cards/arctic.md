# ARCTIC

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2023 |
| 机构 | ETH Zurich; University of Amsterdam; Max Planck Institute for Intelligent Systems |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [ARCTIC: A Dataset for Dexterous Bimanual Hand-Object Manipulation](https://openaccess.thecvf.com/content/CVPR2023/html/Fan_ARCTIC_A_Dataset_for_Dexterous_Bimanual_Hand-Object_Manipulation_CVPR_2023_paper.html) |
| 项目 / 数据 | https://arctic.is.tue.mpg.de/; https://arctic.is.tue.mpg.de/download.php |
| 代码 | https://github.com/zc-alexfan/arctic |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 双手 |
| 采集条件 | 实验室 |
| 场景 | 动捕棚 / 关节物体交互 |
| 采集设备 | 9 机位同步 RGB 系统；54 台 Vicon Vantage-16 红外动捕相机；3dMD 人体扫描仪；Artec 物体扫描仪 |
| 相机设置 | 人类第一视角：1 台佩戴式 RGB 相机、移动；第三视角：8 台固定 RGB 相机 |
| 实际采集数据 | 9 路同步 RGB；人体、手、物体与第一视角相机的光学标记轨迹；人体与物体 3D 扫描 |
| 已发布数据 | 九视角 RGB；相机标定；手部 / 身体 / 物体模型与扫描 |

## 监督信号与数据构建

- 手部 / 身体位姿 ← Vicon 动捕 + 扫描 + MoSh++ / SMPL-X / MANO 拟合。
- 相机 / 物体位姿 ← 动捕 + 标定 / 扫描配准。
- 接触 ← 拟合网格几何。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 339 个序列；210 万张图像；10 名参与者；2 类采集意图 |
| 开放与获取 | 受限访问：数据、标注与代码；[官方入口](https://arctic.is.tue.mpg.de/) |

## 模态影响

- 论文的多视角实验表明，增加训练视角可降低手部重建误差，并提高物体运动重建成功率。
- 来源：[论文](https://openaccess.thecvf.com/content/CVPR2023/html/Fan_ARCTIC_A_Dataset_for_Dexterous_Bimanual_Hand-Object_Manipulation_CVPR_2023_paper.html)

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| ArcticNet | 具身感知 | 训练 + 评测 | RGB 视频与双手 / 关节物体监督用于重建连续的 3D 手—物运动 | [ARCTIC 论文](https://arxiv.org/abs/2204.13662) |
| InterField | 具身感知 | 训练 + 评测 | RGB 视频与手—物网格用于估计逐顶点交互距离场 | [ARCTIC 论文](https://arxiv.org/abs/2204.13662) |

## 官方来源

- 论文： [CVPR 2023](https://openaccess.thecvf.com/content/CVPR2023/html/Fan_ARCTIC_A_Dataset_for_Dexterous_Bimanual_Hand-Object_Manipulation_CVPR_2023_paper.html)；[arXiv 完整版与补充材料](https://arxiv.org/html/2204.13662)
- 项目页： https://arctic.is.tue.mpg.de/
- 官方仓库： https://github.com/zc-alexfan/arctic
- 数据页： https://arctic.is.tue.mpg.de/download.php
- 文档： [数据准备与文件大小](https://github.com/zc-alexfan/arctic/blob/master/docs/data/README.md)；[许可证](https://arctic.is.tue.mpg.de/license.html)；[注册](https://arctic.is.tue.mpg.de/register.php)
