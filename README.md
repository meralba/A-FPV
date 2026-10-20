# Autonomous FPV Racing Drone

An open-source project aimed at building an autonomous FPV racing drone following an iterative Kanban workflow, clean code principles, SOLID, and TDD, leveraging ROS 2 Jazzy, PX4 Autopilot (v1.17.0), and high-fidelity simulation.

## Project Structure (Monorepo)
The repository is structured following a clean monorepo approach to maintain separation of concerns while enabling fast iterative development:
* `docker/`: Dockerfiles and configuration scripts for reproducible environments (ROS 2 Jazzy & Micro-XRCE-DDS-Agent).
* `sim/`: Simulation worlds, models, and launch files for Gazebo and PX4 SITL.
* `ws/`: ROS 2 Workspace containing the source code (`ws/src/`) for packages, control logic, and perception nodes, prioritizing decoupled core logic for TDD.

## Workflow & Methodology
This project uses an **iterative Kanban workflow** tracked via GitHub Projects. Software development emphasizes **Clean Code, SOLID principles, and Test-Driven Development (TDD)**, separating pure algorithmic core logic from ROS 2 middleware wrappers.

## Local Quality Assurance (Git Hooks)
To enforce code quality locally, configure the provided hooks before creating any commits:
```bash
sudo apt install pre-commit
pre-commit install
pre-commit install --hook-type pre-push
```

This hook automatically enforces LLVM code styling via clang-format and ensures all source files terminate with a trailing newline.

## Current Status

**Stage 0 & 1** completed. The containerized simulation environment is fully operational with active uXRCE-DDS transport validation between PX4 and ROS 2 Jazzy (/fmu/in/... and /fmu/out/... topics verified) and automated CI/CD pipelines.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
