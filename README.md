# Autonomous FPV Racing Drone

An open-source project aimed at building an autonomous FPV racing drone following agile/Kanban methodologies, clean code principles, SOLID, and TDD, leveraging ROS2, PX4 Autopilot (v1.17.0), and high-fidelity simulation.

## Project Structure (Monorepo)
The repository is structured following a clean monorepo approach to maintain separation of concerns while enabling fast iterative development:
* `docker/`: Dockerfiles and configuration scripts for reproducible environments (ROS2 Jazzy, etc.).
* `sim/`: Simulation worlds, models, and launch files for Gazebo and PX4-SITL.
* `ws/`: ROS2 Workspace containing the source code (`ws/src/`) for packages, control logic, and perception nodes, prioritizing decoupled core logic for TDD.

## Workflow & Methodology
This project uses an **iterative Kanban workflow** tracked via GitHub Projects. Software development emphasizes **Clean Code, SOLID principles, and Test-Driven Development (TDD)**, separating pure algorithmic core logic from ROS2 middleware wrappers.

## Getting Started
Instructions on how to spin up the Docker containers and run the simulation will be added as **Stage 1** progresses.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.