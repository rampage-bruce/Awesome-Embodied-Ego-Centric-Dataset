# First-Person Hand Action Benchmark (FPHA)

## 概览

| 字段 | 内容 |
| --- | --- |
| 年份 | 2018 |
| 机构 | Imperial College London; Samsung Research |
| 数据角色 | 带标注的人类第一视角数据 |
| 论文 | [First-Person Hand Action Benchmark with RGB-D Videos and 3D Hand Pose Annotations](https://openaccess.thecvf.com/content_cvpr_2018/html/Garcia-Hernando_First-Person_Hand_Action_CVPR_2018_paper.html) |
| 项目 / 数据 | [项目页](https://guiggh.github.io/publications/first-person-hands/)；下载方式见官方仓库 |
| 代码 | https://github.com/guiggh/hand_pose_action |

## 数据采集与发布

| 字段 | 内容 |
| --- | --- |
| 执行主体 | 右手 |
| 采集条件 | 受控真实环境 |
| 场景 | 厨房、办公室与社交场景 |
| 采集设备 | 肩载 Intel RealSense SR300；6 个 trakSTAR 手部磁传感器；物体子集另配磁传感器 |
| 相机设置 | 人类第一视角：肩载式 RGB-D 相机、移动 |
| 实际采集数据 | 同步彩色 / 深度图像；6 路手部 6DoF 磁传感器；物体子集另含物体 6DoF 磁传感器 |
| 已发布数据 | RGB-D；物体网格 |

## 监督信号与数据构建

- 手部 / 手腕位姿 ← 磁跟踪器 + 逆运动学。
- 物体位姿 ← 磁跟踪器 + 扫描标定。
- 动作 ← 脚本化类别体系 / 人工整理。

## 规模与获取

| 字段 | 内容 |
| --- | --- |
| 数据规模 / 任务 | 1,175 段视频；105,459 个 RGB-D 帧；6 名参与者；45 个动作类别 |
| 开放与获取 | 受限访问：数据、标注与示例代码；[官方入口](https://guiggh.github.io/publications/first-person-hands/) |

## 模态影响

- JOULE 动作识别结果中，彩色图像为 66.78%，深度为 60.17%，手部位姿为 74.60%，三者融合达到 78.78%。
- 来源：[论文](https://openaccess.thecvf.com/content_cvpr_2018/html/Garcia-Hernando_First-Person_Hand_Action_CVPR_2018_paper.html)

## 具身智能使用

| 方法 | 方法类别 | 使用阶段 | 使用的数据 | 证据 |
| --- | --- | --- | --- | --- |
| EgoSteer | 决策 / 动作 | 预训练 | 第一视角片段经 EgoSmith 统一为训练样本；保留 0.5 小时 / 578 个片段 | [EgoSteer 论文](https://arxiv.org/abs/2607.09701) |

## 官方来源

- 论文： [CVPR 2018](https://openaccess.thecvf.com/content_cvpr_2018/html/Garcia-Hernando_First-Person_Hand_Action_CVPR_2018_paper.html)；[arXiv](https://arxiv.org/abs/1704.02463)
- 项目页： https://guiggh.github.io/publications/first-person-hands/
- 官方仓库： https://github.com/guiggh/hand_pose_action
- 数据页： [下载与数据结构](https://github.com/guiggh/hand_pose_action#downloading-the-data)
- 文档： [官方仓库说明](https://github.com/guiggh/hand_pose_action#dataset-structure)
