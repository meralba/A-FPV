# Contributing Guidelines

Thank you for contributing to the Autonomous FPV Racing Drone project. To maintain high code health, reliability, and architectural cleanliness across the monorepo, please adhere to the following standards.

## Development Workflow
This project follows an **iterative Kanban workflow**. All developments, bug fixes, or enhancements should be carried out through feature branches and reviewed via Pull Requests targeting the `develop` branch.

## Software Engineering Standards
* **Language:** Modern C++ (C++17/C++20) for control and core algorithms, Python 3 for auxiliary scripts.
* **Architecture (SOLID & Clean Code):**
  * Pure control, kinematics, and mathematical logic must be strictly decoupled from ROS 2 nodes and middleware wrappers (Dependency Inversion Principle).
  * ROS 2 nodes must only handle communication interfaces and message passing (Single Responsibility Principle).
* **No Comments:** Code must be fully self-documenting through clear, domain-driven naming conventions and small, focused functions. Do not include redundant or inline comments.
* **Test-Driven Development (TDD):**
  * Write unit tests (using GoogleTest for C++) before implementing core logic.
  * Ensure all tests pass locally and on the CI pipeline before submitting code.

## Code Style & Formatting
* **C++ Style:** LLVM Style enforced strictly via `.clang-format`.
* **File Termination:** All source and header files (`.cpp`, `.hpp`, `.cc`, `.h`) must end with a single trailing newline.

## Local Quality Assurance (Git Hooks)
To prevent formatting and style errors from reaching the remote repository, install the local hooks before making any commits:

```bash
sudo apt install pre-commit
pre-commit install
pre-commit install --hook-type pre-push
```
This hook automatically checks for a trailing newline and validates compliance with the LLVM `clang-format` rules.

## Related Documentation

* Refer to the [README.md](README.md) for overall project structure and setup instructions.
* Track project milestones and tasks in the ROADMAP.md
