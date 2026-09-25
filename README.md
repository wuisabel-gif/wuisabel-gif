# Hi, I'm Isabella 👋

Most of what I build starts as a problem in my own life. The fix is usually more interesting than the problem, so I keep going until it's a tool other people can use too.

🔬 **Research.** [**CURVE**](https://viterbiundergrad.usc.edu/research/curve/) researcher in RoboLAND at USC, working on how legged robots can feel the ground they walk on.

## Things I built because I needed them

🐋 **[MemWhale](https://github.com/wuisabel-gif/MemWhale)**. My coding agents kept forgetting what they'd already learned, so I built a local-first terminal memory system that records what actually happened while you debug and serves it back to any agent over MCP. Nothing leaves your machine. `cargo install memorywhale-cli`

🎵 **[Cadence](https://github.com/wuisabel-gif/Cadence)**. AI writing has a tell. Cadence catches it, shows you exactly why a draft reads as robotic, and rewrites it in a voice you choose. Zero dependencies, and it runs in Claude Code, Codex, Gemini, Grok, DeepSeek, the browser, and the command line. Try the [score page](https://wuisabel-gif.github.io/Cadence/check.html) with no install.

📡 **[WireDAQ](https://github.com/wuisabel-gif/WireDAQ)**. You shouldn't need the hardware to start. WireDAQ simulates a data-acquisition system end to end so the software and firmware grow against one shared packet contract instead of colliding at bring-up. Python core, C/C++ firmware codec, experimental Rust backend with Lua scenarios, plus **[WireDAQ Health](https://github.com/wuisabel-gif/Wiredaq-health)**, a small Nim CLI for checking live or captured telemetry. [Live demo](https://wuisabel-gif.github.io/WireDAQ/) · `pip install wiredaq`

## Student Lab Involvement

🌊 **[USC AUV](https://uscfrl.com).** Building localization, state estimation, and mission planning for [**Barracuda 2.0**](https://drive.google.com/file/d/1BrcK6pGdd4CBl9zglACMc6I8wHD-CQNz/view), our autonomous underwater vehicle. Two tools came out of that work:
- **[FlashICP](https://github.com/wuisabel-gif/FlashICP)**: CUDA-accelerated point-cloud registration in C++17, heading toward LiDAR odometry on Jetson hardware
- **[ThrusterHelper.jl](https://github.com/wuisabel-gif/ThrusterHelper.jl)**: Julia toolkit for thruster allocation and stress-testing a vehicle's design before it touches water

🚀 **[USC Rocket Propulsion Lab](https://www.uscrpl.com/).** Embedded data-acquisition pipelines, sensor drivers, and high-speed telemetry for rocket avionics.

🔌 **Teaching.** I TA USC's [**TAC 348: Making Smart Devices**](https://reparke.github.io/TAC348-Making-Smart-Devices/), helping students through embedded hardware, sensors, circuits, and connected-device projects.

## Upstream

I contribute to the tools I use.
- **[ONNX Runtime](https://github.com/microsoft/onnxruntime)** (Microsoft): [added GRU operator support](https://github.com/microsoft/onnxruntime/pull/29840) to the WebGPU backend
- **[RocketPy](https://github.com/RocketPy-Team/RocketPy)**: fixed a [delayed-thrust rail takeoff bug](https://github.com/RocketPy-Team/RocketPy/pull/1085) and [hardened the VTK animation tests](https://github.com/RocketPy-Team/RocketPy/pull/1084)
- **[Mbed CE](https://github.com/mbed-ce/mbed-os)**: bug fixes, hardware support, and security-library upgrades
- **[Rerun](https://github.com/rerun-io/rerun/pull/12858)**: clearer errors for glTF/GLB models that need unsupported compression extensions
- **[rho](https://github.com/matthewyjiang/rho)** and **[CodeWhale](https://github.com/Hmbown/CodeWhale)**: regular contributor to these open-source Rust agent harnesses
- **[Jan](https://github.com/janhq/jan)** and **[LocalAI](https://github.com/mudler/LocalAI)**: merged security fixes

## Let's build something

💬 Everything here is open source. PRs are welcome. Half-formed idea or a specific question? Open an issue and let's talk it through.

📚 [Convictions](CONVICTIONS.md) · [Writing](WRITING.md)
