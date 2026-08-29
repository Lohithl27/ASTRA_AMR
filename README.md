# ASTRA AMR 🤖

**ASTRA AMR** is a ROS 2-based Autonomous Mobile Robot (AMR) software project focused on building a modular platform for **robot description, sensor integration, localization, mapping, navigation, control, and system bring-up**.

The repository is organized as a complete development workspace, with the main ASTRA stack separated from ROS 2 foundation and learning material.

> **Project status:** Active development 🚧  
> The repository structure and individual packages are being built and validated incrementally.

---

## 📌 What is ASTRA AMR?

ASTRA AMR is intended to provide a modular software foundation for an autonomous mobile robot. The architecture is divided into dedicated ROS 2 packages so that individual subsystems can be developed, tested, and maintained independently.

### Core areas

- 🧩 **Robot Description** — URDF / robot model and visualization
- 🔩 **Firmware & Hardware Integration** — low-level hardware interfaces and robot I/O
- 🎮 **Controller** — motion and command control
- 📍 **Localization** — estimating the robot pose within its environment
- 🗺️ **Mapping** — building and working with maps
- 🧭 **Navigation** — autonomous path planning and movement
- 🚀 **Bringup** — launching and integrating the complete robot stack
- 📡 **LiDAR** — integration with `rplidar_ros`
- 🛠️ **Scripts & Media** — supporting utilities, resources, and development tools

---

## 🏗️ Repository Structure

```text
ASTRA_AMR/
│
├── astra_ws/                         # Main ASTRA ROS 2 workspace
│   └── src/
│       ├── astra_media/             # Media/resources used by the project
│       ├── astra_firmware/          # Hardware / firmware integration
│       ├── astra_mapping/           # Mapping-related packages and nodes
│       ├── astra_navigation/        # Autonomous navigation stack
│       ├── astra_scripts/            # Utility and helper scripts
│       ├── astra_localization/      # Localization components
│       ├── astra_controller/        # Robot motion/control interfaces
│       ├── astra_bringup/            # System launch and integration
│       ├── astra_description/       # Robot description / URDF
│       └── rplidar_ros/              # RPLIDAR ROS 2 integration
│
└── ROS2_Foundation/                 # ROS 2 learning and foundation workspace
    └── turtle_ws/
        └── src/
            ├── custom_msgs/         # Custom ROS 2 messages and services
            └── turtle_py/           # Python ROS 2 examples and nodes
```

---

## 🧠 Architecture Overview

```text
                    ┌─────────────────────┐
                    │    ASTRA Bringup    │
                    │  System Integration │
                    └──────────┬──────────┘
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼
   ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
   │ Description │     │ Controller  │     │  Firmware   │
   └──────┬──────┘     └──────┬──────┘     └──────┬──────┘
          │                   │                    │
          └───────────────────┼────────────────────┘
                              │
                              ▼
                       ┌─────────────┐
                       │    Sensors  │
                       │   / LiDAR   │
                       └──────┬──────┘
                              │
                 ┌────────────┴────────────┐
                 ▼                         ▼
        ┌────────────────┐        ┌────────────────┐
        │  Localization  │        │     Mapping    │
        └────────┬───────┘        └────────┬───────┘
                 └────────────┬────────────┘
                              ▼
                       ┌─────────────┐
                       │ Navigation  │
                       └─────────────┘
```

The exact node graph, topics, parameters, launch files, and package dependencies will evolve as development progresses.

---

## 🛠️ Technology Stack

- **ROS 2**
- **Ubuntu Linux**
- **Python**
- **C / C++** where required by hardware or ROS 2 components
- **URDF / Robot Description**
- **RViz 2** for visualization
- **Gazebo / simulation tools** where applicable
- **LiDAR integration** through `rplidar_ros`
- **Git & GitHub** for version control

> Some tools and hardware interfaces may vary depending on the current ASTRA hardware configuration.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Lohithl27/ASTRA_AMR.git
cd ASTRA_AMR
```

### 2. Enter the main workspace

```bash
cd astra_ws
```

### 3. Source ROS 2

For a typical ROS 2 installation:

```bash
source /opt/ros/<ros2-distro>/setup.bash
```

Replace `<ros2-distro>` with the ROS 2 distribution installed on your system.

### 4. Build the workspace

```bash
colcon build --symlink-install
```

### 5. Source the workspace

```bash
source install/setup.bash
```

### 6. Verify packages

```bash
ros2 pkg list | grep astra
```

Package names and launch commands should be taken from the current package definitions as development continues.

---

## 📚 ROS 2 Foundation Workspace

The `ROS2_Foundation` directory contains supporting ROS 2 learning material and example packages used during development.

It currently includes examples for:

- Publishers and subscribers
- Services and clients
- Custom messages
- Python ROS 2 nodes
- Turtle simulation exercises

This workspace is kept separate from the main ASTRA robot stack to make the project structure easier to understand and maintain.

---

## 🔭 Development Roadmap

The project is being developed toward a complete autonomous mobile robot platform.

### Planned / ongoing areas

- [ ] Validate the complete ASTRA ROS 2 workspace build
- [ ] Integrate and test robot description in RViz 2
- [ ] Complete hardware and firmware interfaces
- [ ] Validate LiDAR publishing and sensor frames
- [ ] Integrate localization
- [ ] Configure mapping / SLAM workflow
- [ ] Configure navigation and path planning
- [ ] Integrate controller and motor commands
- [ ] Create a unified ASTRA bringup launch system
- [ ] Add simulation support
- [ ] Document topics, services, parameters, and TF frames
- [ ] Add reproducible setup and testing instructions

---

## 🧪 Development & Testing

Before deploying changes to the robot, the recommended workflow is:

```text
Code / Package Change
        ↓
Build with colcon
        ↓
Run ROS 2 package tests
        ↓
Verify topics / TF / nodes
        ↓
Test in simulation when available
        ↓
Test on hardware
        ↓
Document the change
```

For Python packages, standard ROS 2 tests such as `pytest`, `flake8`, and `pep257` may be used where configured by the package.

---

## 📂 Documentation

As the project grows, documentation should cover:

- Hardware architecture
- Software architecture
- ROS 2 package responsibilities
- Topic and service interfaces
- TF tree
- Sensors and frames
- Launch files
- Parameters
- Simulation setup
- Hardware setup
- Troubleshooting

Project-specific documentation can be added to the repository as Markdown files under dedicated documentation directories.

---

## 🤝 Contributing

Contributions and improvements are welcome during development.

A typical contribution workflow is:

```bash
git checkout -b feature/your-feature
git add .
git commit -m "Describe the change"
git push origin feature/your-feature
```

Then open a Pull Request describing:

1. What changed
2. Why it changed
3. How it was tested
4. Any hardware or configuration requirements

---

## ⚠️ Current Status & Notes

ASTRA AMR is an evolving robotics project. Not every package listed in the architecture is necessarily complete or production-ready yet.

Before running the stack on physical hardware, verify:

- ROS 2 distribution compatibility
- Hardware connections
- Sensor configuration
- Motor/controller configuration
- TF frames
- Launch parameters
- Safety limits and emergency-stop behavior

Never assume a software configuration is safe for a physical robot without validating it on the actual hardware.

---

## 👤 Maintainer

**Lohith M R**  
GitHub: [@Lohithl27](https://github.com/Lohithl27)

---

## 📜 License

A project license has not yet been specified in this repository. Add a `LICENSE` file when the licensing terms for ASTRA AMR are decided.

---

⭐ **ASTRA AMR — building a modular ROS 2 foundation for autonomous mobile robotics.**
