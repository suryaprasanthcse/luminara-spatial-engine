# LUMINARA

An AR card-scanning puzzle game in three acts, built in Unity 6 by **Surya Prasanth R** (Sovereign Dynamics).

You point the phone at the floor, then scan cards. Each card opens the next part of the world: the Keystone card, the Anchor card, then the climb to the Tholos. A swarm of boids (simple flocking agents) guides you, and it runs entirely on the GPU.

## How it came to be

LUMINARA started as a prototype at the Funobotz Discovery World hackathon, where entries had to register as a team of three. The three-act game in this repository is my own build: I designed it and directed the work, and Claude Code (Anthropic) wrote the code.

## What's inside

- **GPU boid swarm** (`Assets/BoidSwarmEngine/CurlSwarm`): simulated in a compute shader and drawn with one indirect draw call. It uses no per-agent GameObjects and reads nothing back to the CPU. The default size is 16,384 agents.
- **The three-act loop** (`Assets/BoidSwarmEngine/Hybrid`): `HybridLoopDirector` runs the acts, with card gates and the reactions that open doors, gates and arches.
- **AR card tracking**: AR Foundation image tracking with 5 reference images (`Assets/AR_Targets.asset`).
- **Editor tools** (`Assets/Editor`): scripts that build the AR rig, inject the targets, and assemble each scene.

## Open it

1. Install **Unity 6000.6.0f1**, with the Android Build Support module.
2. Open this folder in Unity Hub. The first import takes a few minutes.
3. Open `Assets/Scenes/Phase5_TrojanHorse.unity`, the main scene.
4. Press Play. In the Editor, XR Simulation stands in for the phone: press **F** to aim the simulated phone at a card.

**Target:** Android, ARM64, IL2CPP, OpenGL ES 3, minimum API 27.

## Rights

- **The code, scenes, shaders, materials and editor tools:** © 2026 Surya Prasanth R. All rights reserved. See `LICENSE`.
- **The Funobotz kit imagery:** the five card faces (`all_knowing_eye.jpg`, `joker.jpg`, `king of spades.jpeg`, `queen_of_hearts.jpg`, `valentoro.jpg`) and the Petalo cutout (`petalo_transparent.png`) came with the hackathon's Funobotz kit. They belong to their owners and aren't covered by this copyright.
- **Unity packages** keep their own licences.
