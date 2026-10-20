# Roadmap: Autonomous FPV Racing Drone

## Project Objective
To develop an autonomous control system for an FPV racing drone capable of navigating circuits autonomously, starting with a simulation environment (ROS2 + PX4) and scaling towards real hardware, driven by clean architecture and TDD.

---

## Stage 0: Environment Definition and Setup (Status: Completed ✅)
- [x] Create the GitHub repository and set up folder structures (`ws/src/`, `docker/`, `sim/`)[cite: 1].
- [x] Configure GitHub Projects (Kanban board for agile task tracking).
- [x] Establish architecture choices: Monorepo, ROS2, PX4 Autopilot, and TDD/SOLID guidelines.

## Stage 1: Simulation Environment Setup (Status: Completed ✅)
- [x] **Task 1.1:** Structure initial Monorepo (`ws/src/`, `docker/`, `sim/`)[cite: 1].
- [x] **Task 1.2:** Create base Dockerfile for ROS2 Jazzy with development tools.
- [x] **Task 1.3:** Configure containerized PX4 Autopilot SITL and Gazebo via Docker Compose.
- [x] **Task 1.4:** Integrate Micro-XRCE-DDS agent for communication bridge.
- [x] **Task 1.5:** Verify basic teleoperation and ROS 2 topic communication.

## Stage 2: Iterative Feature Development (Status: Pending 🛑)
- [ ] **Iteration 2.1:** Basic waypoint-guided autonomous flight via ROS2 (applying TDD to core navigation logic).
- [ ] **Iteration 2.2:** Integration of vision sensors (virtual FPV camera) and perception nodes.
- [ ] **Iteration 2.3:** State estimation algorithms and aggressive control for racing circuits.