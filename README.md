Project Title
🐭 Micromouse Autonomous Maze Solver
🚀 Overview

This project is an autonomous micromouse robot designed to solve unknown mazes using real-time mapping, flood fill path planning, and sensor-based control.

The robot is capable of:

Exploring unknown mazes
Building internal map representation
Computing shortest path using flood fill
Executing high-speed optimized runs
⚙️ Hardware Architecture
Microcontroller: Teensy 2.0
Motors: N20 DC motors with encoders
Distance Sensors: VL53L0X ToF (x3)
IMU: MPU6050
Motor Driver: TB6612FNG / DRV8833 (optional upgrade)
🧠 Core Algorithms
1. Flood Fill Path Planning

The maze is represented as a grid where each cell stores its distance to the goal.

Each step, the robot moves toward the lowest-cost neighbor.

2. PID Control System

Used for:

Wall following
Speed stabilization
Turning accuracy
3. State Machine

Robot operates in two modes:

EXPLORE MODE → builds maze map
SPEED RUN MODE → executes optimal path
📡 Sensor Fusion

The system uses multiple sensors:

IR sensors → fast wall detection
ToF sensors → distance estimation
Encoders → motion tracking
IMU → angular correction
🧱 System Architecture

Sensor Layer → Perception → Mapping → Decision → Motion → Control

🏁 Performance Goals
Solve 16×16 maze
Find optimal path
Execute speed run with minimal turns
Maintain stability at high speed
