# 3D Maze Game

**A first-person maze built with C++ and OpenGL.**

Explore a 20 × 20 maze, collect the red cubes, and reach the golden goal. The project brings together camera movement, collision checks, texture loading, lighting, and a small game loop.

`C++` · `OpenGL` · `GLUT` · `Windows / Visual Studio`

[Build & run](#build--run) · [Controls](#controls) · [Inside the project](#inside-the-project)

This repository is a fork of [MohamedSayedAbdelrazek/3D-Maze-Game](https://github.com/MohamedSayedAbdelrazek/3D-Maze-Game). Credit belongs to the upstream project and its contributors.

---

## Gameplay

- Navigate with a first-person camera and mouse look.
- Collect every red cube before entering the goal cell.
- Fire a projectile with Space.
- Toggle collision, wireframe rendering, lighting, and textures to inspect how the scene works.

The goal remains locked until all collectibles are picked up. Its pulsing animation makes it easier to identify.

## Build & run

The checked-in solution targets **Windows**, the **Visual Studio 2022 v143 toolset**, and the original GLUT library. It is not configured as a portable Linux build.

1. Install Visual Studio's **Desktop development with C++** workload.
2. Provide matching GLUT headers, import library, and runtime DLL.
3. Open [3DMazeGame.sln](3DMazeGame.sln).
4. Select **Debug | Win32** when using the standard 32-bit `glut32.lib`.
5. Set the debugger's working directory to `$(ProjectDir)` so relative asset paths resolve.
6. Build with **F7**, then run with **F5**.

The linker expects `glut32.lib`, `opengl32.lib`, and `glu32.lib`. Keep `glut32.dll` available beside the executable if it is not already on the runtime search path.

The repository includes [stb_image.h](stb_image.h) and the [texture assets](assets). See [SETUP.md](SETUP.md) for the existing detailed setup guide. The renderer tries JPG filenames first and falls back to the included PNG textures.

## Controls

| Input | Action |
| :--- | :--- |
| W / S or Up / Down | Move forward / backward |
| A / D or Left / Right | Strafe |
| Mouse | Look around |
| Space | Fire a projectile |
| Q | Toggle wireframe |
| C | Toggle wall collision |
| L | Toggle lighting |
| T | Toggle textures |
| Esc | Exit |

## Inside the project

| File | Responsibility |
| :--- | :--- |
| [main.cpp](main.cpp) | Window setup, callbacks, and update timer |
| [Game.h](Game.h) | Maze, collectibles, projectiles, and win condition |
| [Camera.h](Camera.h) | Camera position and orientation |
| [Collision.h](Collision.h) | Movement and collision checks |
| [Renderer.h](Renderer.h) | Scene rendering |
| [Lighting.h](Lighting.h) | Lighting configuration |
| [TextureLoader.h](TextureLoader.h) | Image loading and OpenGL textures |
| [Input.h](Input.h) | Keyboard and mouse handling |

The project compiles one `.cpp` translation unit; the other modules contain their implementations in headers.

## Further reading

[Technical documentation](Documentation.md) · [Controls reference](CONTROLS.txt) · [Setup guide](SETUP.md)
