# ASTRA AMR

ASTRA AMR is a ROS 2–based Autonomous Mobile Robot (AMR) project.

## Overview

This repository is organized into:

- **`astra_ws/`**: Main ROS 2 workspace for the ASTRA robot stack.
- **`ROS2_Foundation/`**: Learning and foundation workspace for ROS 2 practice (`turtle_ws`).

## Repository Structure

```text
ASTRA_AMR/
├── astra_ws/
│   └── src/
│       ├── astra_bringup/
│       ├── astra_controller/
│       ├── astra_description/
│       ├── astra_firmware/
│       ├── astra_localization/
│       ├── astra_mapping/
│       ├── astra_media/
│       ├── astra_navigation/
│       └── astra_scripts/
└── ROS2_Foundation/
    └── turtle_ws/
```

## ASTRA Workspace Packages (`astra_ws/src`)

- **`astra_bringup`** – launch and startup orchestration
- **`astra_controller`** – robot control-related components
- **`astra_description`** – robot model/description resources
- **`astra_firmware`** – firmware-facing integration assets
- **`astra_localization`** – localization-related modules
- **`astra_mapping`** – mapping stack components
- **`astra_media`** – media and related resources
- **`astra_navigation`** – navigation stack components
- **`astra_scripts`** – utility and support scripts

## ROS2 Foundation Workspace

The `ROS2_Foundation/turtle_ws` directory contains a separate learning workspace and has its own detailed README:

- [`ROS2_Foundation/turtle_ws/README.md`](ROS2_Foundation/turtle_ws/README.md)
