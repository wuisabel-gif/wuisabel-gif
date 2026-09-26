# Hi, I'm Isabella 👋

Most of what I build starts as a problem in my own life. The fix is usually more interesting than the problem, so I keep going until it's a tool other people can use too.

I study Computer Engineering and Computer Science at USC, and I work across the whole stack: robots and embedded firmware at the bottom, GPU and ML infrastructure in the middle, developer tools and games at the top.

**50 merged upstream PRs across 15 projects** · **[MemWhale](https://github.com/wuisabel-gif/MemWhale): 120★** · **Kaggle top 3%** · **7 games you can play in the browser**

**Jump to:** [Robotics](#-robotics--autonomy) · [Embedded](#-embedded--systems) · [GPU & ML](#-gpu-ml--inference) · [Dev Tools](#%EF%B8%8F-developer-tools) · [Games](#-games) · [Upstream](#-upstream)

---

## 🤖 Robotics & Autonomy

🌊 **[USC AUV](https://uscfrl.com), Software Co-Lead.** Building localization, state estimation, and mission planning for [**Barracuda 2.0**](https://drive.google.com/file/d/1BrcK6pGdd4CBl9zglACMc6I8wHD-CQNz/view), our autonomous underwater vehicle: a ROS 2/GTSAM estimator fusing IMU, DVL, depth, and stereo point clouds, plus a behavior-tree mission planner. Three tools came out of that work:
- **[AUVSimBench](https://github.com/wuisabel-gif/AUVSimBench)**: a ROS 2 physics twin of the vehicle. It publishes the same sensor streams as the real robot, plus ground truth, and can fail a sensor on cue, so we can test the whole stack on a laptop instead of burning pool time
- **[FlashICP](https://github.com/wuisabel-gif/FlashICP)**: CUDA-accelerated point-cloud registration in C++17, heading toward LiDAR odometry on Jetson hardware
- **[ThrusterHelper.jl](https://github.com/wuisabel-gif/ThrusterHelper.jl)**: Julia toolkit for thruster allocation and stress-testing a vehicle's design before it touches water

🔬 **Research.** [**CURVE**](https://viterbiundergrad.usc.edu/research/curve/) researcher in RoboLAND at USC, working on how legged robots can feel the ground they walk on.

## ⚡ Embedded & Systems

🚀 **[USC Rocket Propulsion Lab](https://www.uscrpl.com/).** Embedded data-acquisition pipelines, sensor drivers, and high-speed telemetry for rocket avionics on STM32 and Mbed OS.

📡 **[WireDAQ](https://github.com/wuisabel-gif/WireDAQ)**. You shouldn't need the hardware to start. WireDAQ simulates a data-acquisition system end to end so the software and firmware grow against one shared packet contract instead of colliding at bring-up. Python core, C/C++ firmware codec, experimental Rust backend with Lua scenarios, plus **[WireDAQ Health](https://github.com/wuisabel-gif/Wiredaq-health)**, a small Nim CLI for checking live or captured telemetry. [Live demo](https://wuisabel-gif.github.io/WireDAQ/) · `pip install wiredaq`

## 🧠 GPU, ML & Inference

🔴 **[Morpheus](https://github.com/wuisabel-gif/Morpheus)**. Most LLM benchmarks report one average and call the service fast. Morpheus measures serving performance on vLLM as a distribution: it separates prefill from decode, finds the concurrency point where throughput stops improving, and flags p99 numbers that don't have enough samples behind them.

🧬 **[MoA Prediction](https://github.com/wuisabel-gif/biological-response-modeling)**. A multi-label ML pipeline for predicting how compounds act on cells from 872 gene and cell features, built with NumPy, pandas, scikit-learn, and PyTorch. Finished in the top 3% of the Kaggle leaderboard.

⚡ **FlashICP** (above) for CUDA, and my **[ONNX Runtime](https://github.com/microsoft/onnxruntime/pull/29840)** contribution (below) for GPU inference.

## 🛠️ Developer Tools

🐋 **[MemWhale](https://github.com/wuisabel-gif/MemWhale)**. My coding agents kept forgetting what they'd already learned, so I built a local-first terminal memory system that records what actually happened while you debug and serves it back to any agent over MCP. Nothing leaves your machine. `cargo install memorywhale-cli`

🔀 **[SwapAI](https://github.com/wuisabel-gif/SwapAI)**. One shell-first CLI for Ollama, llama.cpp, and vLLM behind a single OpenAI-compatible API. Plain POSIX shell, tested in CI across sh, bash, and dash.

🎵 **[Cadence](https://github.com/wuisabel-gif/Cadence)**. AI writing has a tell. Cadence catches it, shows you exactly why a draft reads as robotic, and rewrites it in a voice you choose. Zero dependencies, and it runs in Claude Code, Codex, Gemini, Grok, DeepSeek, the browser, and the command line. Try the [score page](https://wuisabel-gif.github.io/Cadence/check.html) with no install.

## 🎮 Games

I'm passionate about games, and most of mine run in the browser. The 3D ones can take a moment to load, but they get there. Click play and you're in.

🟨 **[Backrooms Level 0](https://github.com/wuisabel-gif/backroom_level_0)**. Level 0 rebuilt in Three.js, with no game engine. The rooms stream in forever, something starts hunting you after about 15 seconds, and the only way out is answering lore questions at the M.E.G. terminals. Sometimes you meet another wanderer. It might be a survivor who helps you, or a Skin-Stealer wearing somebody's face. You have to guess. [📺 Gameplay video](https://www.youtube.com/watch?v=mtCEmOLThiI&t=34s)

🎓 **[University of Spoiled Children](https://github.com/wuisabel-gif/university-of-spoiled-children)**. A walkable, Roblox-style USC campus that teaches Cal Newport's *How to Win at College*. Walk up to a signboard to learn a strategy, collect all 16, and you graduate. The whole world is one HTML file, and it works in VR too. [▶ Play](https://wuisabel-gif.github.io/cube/) · [📺 Devlog](https://www.youtube.com/watch?v=m8fQC5L1Y3s)

🏨 **[The Atrium](https://github.com/wuisabel-gif/the-atrium)**. A first-person haunted hotel you explore by lantern light: an Art Deco corridor lined with twelve guest portraits, each with its own unsettling story, and paintings you can step through into the rooms behind them. It doubles as my AI-assisted 3D asset pipeline: the furniture is generated with [Modly](https://github.com/lightningpixel/modly), the UI with a ChatGPT image model, and the lantern, flickering lights, blackouts, and ambient sound are all generated in the browser with no audio files. [▶ Play](https://wuisabel-gif.github.io/the-atrium/) (works on touch too)

🔫 **[Neon Breach](https://github.com/wuisabel-gif/Top-Down-Shooter)**. A neon sci-fi roguelike shooter built with plain HTML, CSS, and JavaScript. Pick a pilot, survive the waves, and unlock bigger weapons. [▶ Play](https://wuisabel-gif.github.io/Top-Down-Shooter/) · [📺 Live play demo](https://youtu.be/rsETcoiq-Rg)

🌻 **[Plants vs. Zombies (C++)](https://github.com/wuisabel-gif/plants_vs_zoombies_cpp)**. My first C++ game: a C++17/SFML remake with plant placement, projectile combat, several zombie types, level progression, and saved progress. [📺 Gameplay video](https://www.youtube.com/watch?v=2EqATLMfwcs&t=14s)

🐣 **[Thronglets](https://github.com/wuisabel-gif/Thronglets)**. Little creatures that live in your terminal, inspired by Black Mirror's "Plaything." They trade ideas when they meet, the ideas mutate as they spread, and a culture forms that you never chose. Feed them, or don't. Written in Rust. `cargo run --release` · [📺 Video](https://www.youtube.com/watch?v=GRO-5Mw0oL4)

🛡️ **[NPC-FSM](https://github.com/wuisabel-gif/npc-fsm)**. An engine-independent NPC behavior library in Squirrel: guards patrol, chase, attack, search, and radio each other for backup. [Project site](https://wuisabel-gif.github.io/npc-fsm/)

## 🔧 Upstream

I contribute to the tools I use.
- **[ONNX Runtime](https://github.com/microsoft/onnxruntime)** (Microsoft): [added GRU operator support](https://github.com/microsoft/onnxruntime/pull/29840) to the WebGPU backend
- **[Mbed CE](https://github.com/mbed-ce/mbed-os)**: bug fixes, hardware support, and security-library upgrades
- **[RocketPy](https://github.com/RocketPy-Team/RocketPy)**: fixed a [delayed-thrust rail takeoff bug](https://github.com/RocketPy-Team/RocketPy/pull/1085) and [hardened the VTK animation tests](https://github.com/RocketPy-Team/RocketPy/pull/1084)
- **[Rerun](https://github.com/rerun-io/rerun/pull/12858)**: clearer errors for glTF/GLB models that need unsupported compression extensions
- **[Proton-GE](https://github.com/GloriousEggroll/proton-ge-custom/pull/674)**: fixed a crash in Star Citizen's message-box hook so the game runs on Linux
- **[Modly](https://github.com/lightningpixel/modly/pull/195)**: added a headless deployment guide for the NVIDIA Jetson AGX Orin
- **[rho](https://github.com/matthewyjiang/rho)** (16 PRs) and **[CodeWhale](https://github.com/Hmbown/CodeWhale)** (14 PRs): regular contributor to these open-source Rust agent harnesses
- **[Jan](https://github.com/janhq/jan)** and **[LocalAI](https://github.com/mudler/LocalAI)**: merged security fixes

## 🔌 Teaching

I am the learning assistant for USC's [**TAC 348: Making Smart Devices**](https://reparke.github.io/TAC348-Making-Smart-Devices/), helping students through embedded hardware, sensors, circuits, and connected-device projects.

## Let's build something

💬 Everything here is open source. PRs are welcome. Half-formed idea or a specific question? Open an issue and let's talk it through.

📚 [Convictions](CONVICTIONS.md) · [Writing](WRITING.md)
