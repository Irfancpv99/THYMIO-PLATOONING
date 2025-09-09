# Thymio Multi-Robot Simulation Project

![Thymio Robot](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgdmlld0JveD0iMCAwIDIwMCAyMDAiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxjaXJjbGUgY3g9IjEwMCIgY3k9IjEwMCIgcj0iODAiIHN0cm9rZT0iIzMzMzMzMyIgc3Ryb2tlLXdpZHRoPSI4IiBzdHJva2UtZGFzaGFycmF5PSI1IDUiIGZpbGw9Im5vbmUiLz4KPGxpbmUgeDE9IjQwIiB5MT0iNDAiIHgyPSI4MCIgeTI9IjgwIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iOCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIi8+CjxsaW5lIHgxPSIxNjAiIHkxPSI0MCIgeDI9IjEyMCIgeTI9IjgwIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iOCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIi8+CjxsaW5lIHgxPSIxNjAiIHkxPSIxNjAiIHgyPSIxMjAiIHkyPSIxMjAiIHN0cm9rZT0iIzMzMzMzMyIgc3Ryb2tlLXdpZHRoPSI4IiBzdHJva2UtbGluZWNhcD0icm91bmQiLz4KPGxpbmUgeDE9IjQwIiB5MT0iMTYwIiB4Mj0iODAiIHkyPSIxMjAiIHN0cm9rZT0iIzMzMzMzMyIgc3Ryb2tlLXdpZHRoPSI4IiBzdHJva2UtbGluZWNhcD0icm91bmQiLz4KPC9zdmc+)

This project demonstrates a multi-robot simulation using Thymio II robots in the Aseba playground environment. The simulation includes four Thymio robots with different behaviors including line following, obstacle avoidance, and overtaking maneuvers.

## Project Overview

The simulation consists of:
- **4 Thymio II robots** with unique behaviors and positioning
- **450x450 cm virtual world** with custom ground texture
- **Line following algorithms** with different implementations
- **Obstacle detection and avoidance** capabilities
- **Robot-to-robot interaction** and overtaking behavior

## Robot Configurations

### Thymio_1 (Node ID: 1)
- **Position**: (155, 240) cm, angle: 10.8 rad
- **Behavior**: Timer-based line following
- **Features**:
  - Dual ground sensor monitoring (left/right)
  - Configurable speed (150 units)
  - Black line detection with threshold levels
  - Differential steering for line tracking

### Thymio_2 (Node ID: 2)
- **Position**: (255, 175) cm, angle: 3.5 rad
- **Behavior**: Event-driven line following
- **Features**:
  - Proximity sensor-based navigation
  - Subroutine-based movement control
  - Left/right turning with speed differential
  - Higher base speed (200 units)

### Thymio_3 (Node ID: 3)
- **Position**: (140, 125) cm, angle: -11.8 rad
- **Behavior**: Advanced line following with overtaking
- **Features**:
  - **Overtaking capability** - can detect and pass other robots
  - LED feedback system for status indication
  - Communication system enabled
  - Obstacle avoidance with horizontal sensors
  - Highest speed (300 units)

### Thymio_4 (Node ID: 4)
- **Position**: (320, 300) cm, angle: -11.8 rad
- **Behavior**: Line following with comprehensive obstacle detection
- **Features**:
  - Multiple proximity sensors monitoring
  - Advanced obstacle detection (front, sides, rear)
  - Combined line following and obstacle avoidance
  - Emergency stop functionality
  - High-performance speed (300 units)

## Technical Specifications

### World Configuration
- **Dimensions**: 450x450 cm
- **Background**: White with custom texture (`homemap.jpg`)
- **Energy Scoring**: Enabled for performance monitoring
- **Camera Position**: Overhead view at (200, 200, 180) cm

### Sensor Thresholds
- **Black Line Detection**: < 200 (Thymio_1, Thymio_4)
- **White Surface**: > 500
- **Obstacle Detection**: > 500-1000 (proximity sensors)
- **Line Following**: < 85-100 (Thymio_2, Thymio_3)

### Color Definitions
- White: RGB(1.0, 1.0, 1.0)
- Yellow: RGB(1.0, 1.0, 0)
- Red: RGB(1.0, 0, 0)
- Blue: RGB(0, 0, 1.0)
- Purple: RGB(0.8, 0.1, 0.7)

## File Structure

```
├── Myground.playground          # Main simulation configuration
├── thymio_1.aesl               # Timer-based line follower
├── thymio_2.aesl               # Event-driven line follower
├── thymio_3.aesl               # Advanced overtaking robot
├── thymio_4.aesl               # Obstacle-aware line follower
└── homemap.jpg                 # Ground texture image
```

## Key Algorithms

### Line Following Methods
1. **Timer-based approach** (Thymio_1): 50ms timer with continuous sensor monitoring
2. **Event-driven approach** (Thymio_2): Proximity event triggers with subroutines
3. **Advanced tracking** (Thymio_3): Combined line following with overtaking logic
4. **Hybrid approach** (Thymio_4): Line following integrated with obstacle detection

### Behavioral Features
- **Differential Steering**: Robots adjust left/right motor speeds for turning
- **Sensor Fusion**: Ground sensors combined with proximity sensors
- **State Management**: Overtaking states and behavioral switching
- **LED Feedback**: Visual indicators for robot status and actions

## Getting Started

### Prerequisites
- Aseba Studio or compatible Thymio programming environment
- Aseba Playground simulator

### Running the Simulation
1. Load `Myground.playground` in Aseba Playground
2. Upload respective `.aesl` files to each robot:
   - `thymio_1.aesl` → Thymio_1
   - `thymio_2.aesl` → Thymio_2
   - `thymio_3.aesl` → Thymio_3
   - `thymio_4.aesl` → Thymio_4
3. Start the simulation to observe multi-robot behaviors

### Customization
- Modify speed variables in each robot's code
- Adjust sensor thresholds for different line/surface types
- Change robot starting positions in the playground file
- Add new behaviors or sensors as needed

## Author
Created by Fanny Riedo (fanny dot riedo at mobsya dot org) in July 2018 for Aseba 1.6

## Notes
- All robots use port 33334 for communication
- The simulation supports energy monitoring for performance analysis
- Ground texture and robot positioning can be customized
- Each robot demonstrates different programming approaches and capabilities
