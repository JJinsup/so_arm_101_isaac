# Isaac Lab – SO‑ARM100 / SO‑ARM101 Project

![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?style=flat-square&logo=ubuntu&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)
![Isaac Sim](https://img.shields.io/badge/Isaac_Sim-5.0.0-000000?style=flat-square&logo=nvidia&logoColor=white)
![Isaac Lab](https://img.shields.io/badge/Isaac_Lab-main-00AA88?style=flat-square&logo=python&logoColor=white)
![Isaac Lab Internal](https://img.shields.io/badge/isaaclab-0.48.5-blue?style=flat-square)


## Environment (Tested Setup)

| 구성 요소 | 세부 사양 |
|----------|-----------|
| CPU / RAM | Intel i9-10900X / 188GB |
| OS | Ubuntu 22.04.5 (kernel 6.8.0-87-generic) |
| GPU | RTX 3090 × 2 |
| NVIDIA-SMI | 575.57.08 |
| CUDA | 12.9 |
| Isaac Lab | `main` branch (Commit Hash: `2ed331acfc`) |
| Python | 3.11 |

## 🛠️ Installation

1. Install Isaac Lab by following the [official installation guide](https://isaac-sim.github.io/IsaacLab/main/source/setup/installation/index.html) (using conda).
2. Clone this repository **outside** the `IsaacLab` directory.
3. Install the package:

   ```bash
   python -m pip install -e source/SO_100
   ```

## 🚀 Quickstart

To list all available environments:

```bash
python scripts/list_envs.py
```

## 🐞 Debugging Tasks

Two scripts can help verify your setup:

**Zero Agent**

Sends zero commands to all robots, confirming that the environment loads correctly:

```bash
python scripts/zero_agent.py --task SO-ARM100-Reach-Play-v0
```

**Random Agent**

Sends random commands to all robots, confirming proper actuation:

```bash
python scripts/random_agent.py --task SO-ARM100-Reach-Play-v0
```

## 🏋️‍♂️ Training and Playback

You can train a policy for SO‑ARM100 / SO‑ARM101 tasks (for example, the **Reach** task, which is a basic RL-based IK) with the `rsl_rl` and/or `skrl` library:

```bash
python scripts/rsl_rl/train.py --task SO-ARM100-Reach-v0 --headless
```

After training, validate the learned policy:

```bash
python scripts/rsl_rl/play.py --task SO-ARM100-Reach-Play-v0
```

This ensures that your policy performs as expected in Isaac Lab before attempting real‑world transfer.

## 📄 License

This project is licensed under the BSD 3-Clause License. See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

This project builds upon the excellent work of several open-source projects and communities:

- **[Isaac Lab](https://isaac-sim.github.io/IsaacLab/)** - The foundational robotics simulation framework that powers this project
- **[NVIDIA Isaac Sim](https://developer.nvidia.com/isaac-sim)** - The underlying physics simulation platform
- **[RSL-RL](https://github.com/leggedrobotics/rsl_rl)** - Reinforcement learning library used for training policies
- **[SKRL](https://github.com/Toni-SM/skrl)** - Alternative RL library integration
- **[SO-ARM100/SO-ARM101 Robot](https://github.com/TheRobotStudio/SO-ARM100)** - The hardware platform that inspired this simulation environment
- **[SO-ARM100/SO-ARM101 Project](https://github.com/MuammerBay/isaac_so_arm101)** - 원본 프로젝트

❌ 주의 사항
1. LICENSE 파일(BSD 3-Clause 전문) 그대로 유지
2. 저작권 문구(Copyright)
3. 저작권자 이름을 가져다가 홍보/광고에 사용하는 것 금지
