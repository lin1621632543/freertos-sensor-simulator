# FreeRTOS Sensor Simulator

A FreeRTOS sensor simulation project running on Linux/POSIX for learning RTOS concepts and embedded software engineering.

## Project Goal

This project simulates a small embedded sensor-control system on Ubuntu Linux without requiring physical MCU hardware.

The main goal is not only to learn FreeRTOS APIs, but also to practice a structured embedded software development workflow including:

- requirements analysis
- modular C design
- Git branch-based development
- build systems
- debugging
- testing
- code review
- continuous integration

## Initial System Design

The first version will use the following data flow:

```text
SensorTask
    |
    v
  Queue
    |
    v
FilterTask
    |
    v
ControlTask
    |
    v
LoggerTask
```

### SensorTask

Generates simulated temperature data every 1 second.

### FilterTask

Processes sensor data using a moving average filter with a window size of 5 samples.

### ControlTask

Applies a simple temperature control rule:

```text
temperature < 25°C  -> HEATING
temperature >= 25°C -> IDLE
```

### LoggerTask

Provides centralized system status output.

## Planned FreeRTOS Features

The project will gradually introduce:

- Tasks
- Queues
- Mutexes
- Semaphores
- Software Timers
- Event Groups
- Task Notifications
- Task priorities

These features will be added incrementally instead of being implemented all at once.

## Project Structure

```text
freertos-sensor-simulator/
├── README.md
├── LICENSE
├── .gitignore
├── CMakeLists.txt
├── src/
├── include/
└── docs/
```

## Current Status

Current phase: Project setup and architecture design.

No FreeRTOS application code has been implemented yet.