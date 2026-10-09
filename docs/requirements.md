# Project Requirements

## Project

`freertos-sensor-simulator`

## Purpose

Build a FreeRTOS-based sensor simulation application that runs on Ubuntu Linux using the POSIX/GCC environment.

The project does not depend on ESP32, STM32, or physical sensor hardware.

The primary goal is to learn FreeRTOS fundamentals while practicing a structured embedded software development workflow.

## Initial Functional Requirements

The first version of the system shall contain the following logical pipeline:

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

- Generate simulated temperature data.
- Generate one new sample every 1 second.
- Send generated sensor data to the next processing stage.

### FilterTask

- Receive temperature samples.
- Apply a moving average filter.
- Use a filter window of 5 samples.

### ControlTask

- Receive filtered temperature data.
- Apply the following control rule:

```text
temperature < 25°C  -> HEATING
temperature >= 25°C -> IDLE
```

### LoggerTask

- Provide centralized runtime status output.
- Display relevant sensor, filter, and controller information.

## Initial Non-Functional Requirements

- The project shall run on Ubuntu Linux.
- The project shall be written primarily in C.
- The project shall be built using GCC.
- The project shall use CMake or Make as its build system.
- The project shall be organized into separate source and header directories.
- The project shall be managed using Git.
- Development changes shall be performed using branches instead of directly modifying `main`.

## Future FreeRTOS Features

The following features will be introduced incrementally in later versions:

- Queue
- Mutex
- Semaphore
- Software Timer
- Event Group
- Task Notification
- Task priorities

These features shall not all be added to the first implementation.

## Current Status

Version: Requirements v0.1

Status: Initial project definition completed. No FreeRTOS application code has been implemented yet.