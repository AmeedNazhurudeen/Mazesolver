# 🐭 Micromouse Maze Solver Robot

An autonomous micromouse robot designed to solve unknown mazes using real-time mapping, flood fill path planning, and sensor-based closed-loop control.

This project focuses on **embedded robotics, motion control, and intelligent path planning under real-world constraints**.

---

## 🚀 Project Goals

- Explore unknown 16×16 maze environments
- Build an internal map in real-time
- Compute shortest path to the goal cell
- Execute high-speed optimized runs
- Maintain stable motion using PID control

---

## ⚙️ Hardware Overview

- **Microcontroller:** Teensy 2.0 (upgradeable to Teensy 4.0)
- **Motors:** N20 DC motors with encoders
- **Motor Driver:** TB6612FNG / DRV8833 (recommended upgrade)
- **Distance Sensors:** VL53L0X ToF sensors (x3)
- **IMU:** MPU6050 (gyro + accelerometer)
- **Power:** LiPo battery (7.4V recommended)

---

## 🧠 Core System Architecture

The robot is designed as a layered embedded system:


Sensors → Perception → Mapping → Decision → Motion → Control


### Layers:

- **Sensor Layer:** IR / ToF / Encoder / IMU readings
- **Perception Layer:** Wall detection & distance estimation
- **Mapping Layer:** Maze grid construction
- **Decision Layer:** Flood Fill path planning
- **Motion Layer:** Speed profile & turn execution
- **Control Layer:** PID motor control

---

## 🧭 Algorithms Used

### 1. Flood Fill Algorithm (Main Navigation)

Each maze cell is assigned a distance value relative to the goal. The robot always moves toward the lowest-cost neighboring cell.

This ensures:
- Guaranteed shortest path (after full exploration)
- Dynamic adaptation to discovered walls
- Real-time re-planning capability

---

### 2. PID Control System

Used for:
- Wall following stability
- Speed control
- Smooth turning

Inputs:
- Encoder feedback
- IR sensor error

---

### 3. State Machine

The robot operates in two main modes:

- **EXPLORATION MODE**
  - Builds maze map
  - Updates flood fill values dynamically

- **SPEED RUN MODE**
  - Executes optimized shortest path
  - Focuses on maximum speed and stability

---

## 📡 Sensor Strategy

### Primary Sensors:
- IR sensors → real-time wall detection (fast control loop)

### Secondary Sensors:
- VL53L0X ToF → distance estimation & mapping support
- MPU6050 IMU → turning stability and angular correction
- Encoders → precise movement tracking

---

## ⚡ Motion Strategy

- Trapezoidal velocity profile (accelerate → cruise → decelerate)
- Corner smoothing for faster turns
- Straight-line optimization during speed run phase

---

## 🧱 Key Features

- Real-time maze mapping
- Adaptive flood fill path planning
- Sensor fusion-based navigation
- Closed-loop PID motor control
- Exploration + speed run mode switching

---

## 🛠️ Folder Structure


micromouse-maze-solver/
│
├── firmware/ # Embedded robot code
├── hardware/ # PCB, wiring, BOM
├── simulation/ # Maze simulation tools
├── docs/ # Architecture & technical docs
├── tools/ # Calibration & debugging scripts
└── tests/ # Unit tests for algorithms


---

## 📈 Future Improvements

- Upgrade to high-speed microcontroller (Teensy 4.0 / STM32)
- Replace or complement ToF with high-speed IR arrays
- Implement A* hybrid optimization for faster path computation
- Add SLAM-based mapping for advanced research applications
- Improve motion planning using S-curve velocity profiles

---

## 🎯 Applications

- Micromouse robotics competitions
- Autonomous navigation research
- Embedded systems optimization
- Path planning algorithm benchmarking
- Mobile robotics research projects

---

## 🧪 Status

🚧 In Development  
✔ Hardware design ongoing  
✔ Algorithm implementation in progress  
✔ Simulation layer planned  

---

## 📜 License

This project is open-source for educational and research purposes.

---

## 🤖 Author

Built as part of an advanced robotics learning and competition project focused on autonomous navigation systems and embedded intelligence.

---
