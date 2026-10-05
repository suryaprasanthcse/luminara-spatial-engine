# LUMINARA

An AR card-scanning puzzle game in three acts, built in Unity 6 by **Team Nandha - ML** for the Funobotz Discovery World hackathon.

You point the phone at the floor, then scan cards from the Funobotz kit. Each card opens the next part of the world: the Keystone card, the Anchor card, then the climb to the Tholos. A swarm of boids (simple flocking agents) guides you, and it runs entirely on the GPU.

## What's inside

- **GPU boid swarm** (`Assets/BoidSwarmEngine/CurlSwarm`): simulated in a compute shader and drawn with one indirect draw call. It uses no per-agent GameObjects and reads nothing back to the CPU. The default size is 16,384 agents.
- **The three-act loop** (`Assets/BoidSwarmEngine/Hybrid`): `HybridLoopDirector` runs the acts, with card gates and the reactions that open doors, gates and arches.
- **AR card tracking**: AR Foundation image tracking with 5 reference images (`Assets/AR_Targets.asset`).
- **Editor tools** (`Assets/Editor`): scripts that build the AR rig, inject the targets, and assemble each phase's scene.
- **Design documents** (`docs/`): the Phase 2 blueprint, the Phase 3 GDD, the technology and AI declarations, the known limitations, and the pitch draft.

## Open it

1. Install **Unity 6000.6.0f1**, with the Android Build Support module.
2. Open this folder in Unity Hub. The first import takes a few minutes.
3. Open `Assets/Scenes/Phase5_TrojanHorse.unity`, the main scene.
4. Press Play. In the Editor, XR Simulation stands in for the phone: press **F** to aim the simulated phone at a card.

**Target:** Android, ARM64, IL2CPP, OpenGL ES 3, minimum API 27.

## Credits and rights

- **Built by Team Nandha - ML:** [team members].
- **AI use:** Anthropic Claude (through Claude Code) was used under team direction. See `docs/phase3/02_Technology_Asset_AI_Declarations.md` for exactly what it did.
- **Funobotz kit imagery:** the five card faces and the Petalo cutout come from the hackathon-provided Funobotz kit. **Confirm the usage terms before making this repository public.**
- **Everything else** (meshes, shaders, materials) was made by the team, or generated in the editor from Unity primitives.

This project was separated out of a shared Unity project, `MAAYAI_Matrix_AR`, which also holds SYNAPSE-3D. Its development history stayed there. This repository starts from the final state.
