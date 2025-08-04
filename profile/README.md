# Flicker Engine

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Build Status](https://img.shields.io/badge/build-pending-lightgrey)](https://github.com/Flicker-Engine)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)](#contributing)

Flicker Engine is a modern C++ game engine designed on the principles of **minimalism, modularity, and ease of use**. It provides a flexible, data-driven framework for creating a wide range of games, from 2D side-scrollers to 3D first-person experiences.

## Core Philosophy

The engine is built on a foundation of **clear separation of concerns**. Each major component (renderer, physics, ECS, etc.) is developed and compiled into a distinct static library. The main editor executable links these modules together, creating a clean, scalable, and maintainable architecture. This modularity allows developers to use only the parts of the engine they need and simplifies the process of extending or replacing core systems.

## Features

The engine is composed of several independent modules, each with a specific responsibility. Features listed below represent the current and planned capabilities of the engine.

### Core Systems
-   **`Flicker-ECS`**: A modern Entity-Component-System implementation that serves as the backbone for scene organization and game logic.
-   **`Flicker-Utilities`**:
    -   Hashed Asset IDs for fast and robust asset management at runtime.
    -   JSON serialization for human-readable scenes, materials, and prefabs.
    -   An intelligent asset caching system to manage memory.
-   **Threading**:
    -   A high-level thread pool and task management system.
    -   Dedicated threads for rendering, physics, and asset loading.

### Rendering
-   **`Flicker-Renderer-Interface`**: A common interface for all rendering operations, allowing for interchangeable graphics backends.
-   **`Flicker-Vulkan-Backend`**: A modern, high-performance rendering pipeline using the Vulkan API.
-   **`Flicker-OpenGL-Backend`**: A rendering pipeline using the OpenGL API for broader compatibility.
-   **Capabilities**:
    -   A hybrid camera supporting both **perspective** (3D) and **orthographic** (2D) projections.
    -   Multi-mode rendering optimized for 3D meshes, 2D sprites, and debug views.
    -   A library of premade, customizable shaders.

### Physics (`Flicker-Physics`)
-   **Multi-Mode Simulation**:
    -   **3D Physics**: Robust rigid-body dynamics.
    -   **2.5D Physics**: Axis-locking constraints on 3D rigid bodies.
    -   **2D Physics**: A dedicated 2D physics simulation.
-   **Fluid Simulation**: SPH-based (Smoothed-Particle Hydrodynamics) fluid dynamics for realistic liquid effects.

### Scripting APIs
-   **`Flicker-API-Native`**: Native C++ scripting support via a clean virtual interface.
-   **`Flicker-API-Csharp`**: C# scripting integration for rapid development.

### Editor & GUI
-   **`Flicker-Editor`**: The central hub for project development.
    -   A scene editor for visually placing and manipulating entities using **ImGuizmo**.
    -   A timeline-based animation editor for entities and cutscenes.
    -   In-editor visualization of performance metrics (**ImPlot**) and memory usage.
-   **`Flicker-GUI`**:
    -   A fully customizable, dockable editor UI built with **ImGui**.
    -   Support for in-game user interfaces using libraries like **ImRAD**.

### Virtual Reality (`Flicker-VR`)
-   Planned support for VR hardware and interaction via the **OpenXR** standard.

## Supported Game Perspectives

The engine architecture is being built to support a wide variety of game genres out-of-the-box:
-   3D First-Person / Third-Person
-   3D Top-Down (e.g., strategy games)
-   2.5D Side-Scroller (3D world, 2D gameplay)
-   2D Top-Down
-   2D Side-Scroller

## Getting Started

### Prerequisites
1.  A C++ compiler that supports C++23.
2.  [xmake](https://xmake.io/) build system.
3.  Vulkan SDK and/or OpenGL libraries installed on your system.

### Cloning the Repositories
The Flicker Engine is split across multiple repositories. Clone them all into the same parent directory.

```bash
git clone https://github.com/Flicker-Engine/Flicker-Editor.git
git clone https://github.com/Flicker-Engine/Flicker-Renderer-Interface.git
git clone https://github.com/Flicker-Engine/Flicker-ECS.git
git clone https://github.com/Flicker-Engine/Flicker-Physics.git
git clone https://github.com/Flicker-Engine/Flicker-Utilities.git
git clone https://github.com/Flicker-Engine/Flicker-GUI.git
git clone https://github.com/Flicker-Engine/Flicker-API-Native.git
git clone https://github.com/Flicker-Engine/Flicker-API-Csharp.git
git clone https://github.com/Flicker-Engine/Flicker-VR.git
git clone https://github.com/Flicker-Engine/Flicker-OpenGL-Backend.git
git clone https://github.com/Flicker-Engine/Flicker-Vulkan-Backend.git
```

## Building and Running
Navigate to the Flicker-Editor directory and use xmake to build and run the project.
```
# Configure the project (only needs to be done once)
xmake -m release

# Build all engine modules and the editor
xmake

# Run the editor
xmake run flicker-editor
```
## Contributions
To learn more about how to contribute to the project, please refer to our contributor guidelines:
https://github.com/Flicker-Engine/Contributor-Information
