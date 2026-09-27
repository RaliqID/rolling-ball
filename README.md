# Rolling Ball

A Unity rolling-ball game exercise covering the fundamentals of 3D game development: rigidbody physics, player control, camera follow, collectibles, and level structure.

## Overview

A classic "roll a ball around and collect things" project, built deliberately as a learning exercise. The value here is in the structure: gameplay logic is separated into small, single-purpose components, and the project includes editor tooling and tests rather than being a loose scene.

## Features

- **Rigidbody movement** â€” physics-driven ball control with tuned force/acceleration
- **Camera follow** â€” smoothed follow camera tracking the player
- **Collectibles** â€” pickups that trigger game state changes
- **Game manager** â€” central state: score, win/lose conditions, restart
- **Editor tooling** â€” `PlayerBuilder` and `SceneBuilder` construct/test the scene from the editor
- **Tests** â€” `GameLogicTests` and `SmokeTest` verify logic in the editor

## Project Structure

```
Assets/
  Game/                  # Runtime gameplay scripts
    PlayerController.cs  # Movement and input
    CameraController.cs  # Follow camera
    Collectible.cs       # Pickup behaviour
    GameLogic.cs         # Core rules
    GameManager.cs       # State, score, win condition
  Editor/                # Editor-only tooling and tests
    PlayerBuilder.cs
    SceneBuilder.cs
    GameLogicTests.cs    # Unit tests
    SmokeTest.cs         # Scene smoke test
Packages/                # Unity package manifest
ProjectSettings/         # Project configuration
```

## Design Notes

- Gameplay scripts under `Assets/Game/` hold no editor dependencies, so logic stays testable
- `Assets/Editor/` holds everything that only runs in the editor â€” tests and scene builders stay out of builds
- Scene construction is scripted (`SceneBuilder`) so the setup is reproducible rather than hand-placed

## Tech Stack

- Unity
- C#
- Unity Test Framework (editor tests)

## Running

Open the project folder in Unity Hub with a matching Unity version (see `ProjectSettings/ProjectVersion.txt`).

**Author:** Raliq Hidayat BM3
