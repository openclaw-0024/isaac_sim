# Isaac Lab 人形机器人行走训练 - 完整学习路线

通过 NVIDIA Isaac Lab 平台从零学习训练人形机器人行走，涵盖从基础知识到 Sim2Real 实机部署的全流程。

---

## 学习路线总览

```
基础知识准备 → 环境搭建 → 官方教程 → 宇树机器人实操 → 自定义机器人训练 → Sim2Real 部署
  (1-2周)      (1周)     (2-3周)      (2-3周)          (3-4周)          (持续迭代)
```

总预计时间：10-14 周（按照每天 2-4 小时学习）

---

## 文档目录

| 序号 | 文档 | 内容 | 阶段 |
|------|------|------|------|
| 01 | [环境搭建指南](docs/01_环境搭建指南.md) | 系统要求、安装步骤、验证、云端方案 | 第 1 阶段 |
| 02 | [官方教程学习路线](docs/02_官方教程学习路线.md) | CartPole入门、四足locomotion、人形遥操作 | 第 2 阶段 |
| 03 | [宇树机器人实操指南](docs/03_宇树机器人实操指南.md) | H1/G1训练、配置文件解读、奖励函数分析 | 第 3 阶段 |
| 04 | [自定义机器人训练指南](docs/04_自定义机器人训练指南.md) | URDF准备、环境搭建、算法、reward设计 | 第 4 阶段 |
| 05 | [Sim2Real部署指南](docs/05_Sim2Real部署指南.md) | 策略导出、部署架构、常见问题、实测流程 | 第 5 阶段 |
| 06 | [硬件配置与云端方案](docs/06_硬件配置与云端方案.md) | 硬件分档、当前评估、云端服务对比 | 参考 |
| 07 | [推荐学习资源与论文清单](docs/07_推荐学习资源与论文清单.md) | 教材、课程、论文、工具 | 参考 |

---

## 硬件要求速查

| 级别 | GPU | VRAM | 能力 |
|------|-----|------|------|
| 最低 | RTX 3080 | 16GB | 2048 并行环境 |
| 推荐 | RTX 4090 | 24GB | 4096 并行环境 |
| 专业 | A100 | 80GB | 8192+ 并行环境 |

> 目标系统：Ubuntu 24.04 LTS。GPU VRAM 需 >= 16GB，详见 [硬件配置与云端方案](docs/06_硬件配置与云端方案.md)。

---

## 核心技术栈

- **目标系统**: Ubuntu 24.04 LTS
- **仿真平台**: NVIDIA Isaac Sim 5.1.0 + Isaac Lab
- **RL 算法**: PPO (通过 RSL-RL 库)
- **任务框架**: Velocity Tracking Locomotion
- **机器人描述**: URDF → USD
- **ROS 版本**: ROS 2 Jazzy（Ubuntu 24.04 对应版本）
- **部署推理**: ONNX Runtime / TensorRT
- **边缘硬件**: NVIDIA Jetson Orin

---

## 快速开始（环境就绪后）

```bash
# 1. 训练 CartPole（验证环境）
./isaaclab.sh -p scripts/reinforcement_learning/rsl_rl/train.py \
  --task Isaac-Cartpole-v0 --num_envs 1024 --headless

# 2. 训练宇树 H1 行走
./isaaclab.sh -p scripts/reinforcement_learning/rsl_rl/train.py \
  --task Isaac-Velocity-Flat-H1-v0 --num_envs 4096 --headless

# 3. 可视化结果
./isaaclab.sh -p scripts/reinforcement_learning/rsl_rl/play.py \
  --task Isaac-Velocity-Flat-H1-v0 --num_envs 50
```

---

## 关键链接

- Isaac Lab 文档: https://isaac-sim.github.io/IsaacLab/main/
- Isaac Lab GitHub: https://github.com/isaac-sim/IsaacLab
- Getting Started 课程: https://docs.nvidia.com/learning/physical-ai/getting-started-with-isaac-lab/
- NVIDIA 开发者论坛: https://forums.developer.nvidia.com/
