Hello everyone! 

I want to share an experimental project I’ve been building as a passionate hobby: **Rose (RoseScript Canvas)**, a statically-typed declarative UI language designed for ultra-lightweight, hardware-accelerated desktop interfaces. 

To be completely transparent—I am not a professional compiler engineer. I built this out of love for clean UI design and a frustration with modern desktop frameworks. I wanted something as simple and reactive as web development (Svelte/React-style) but with the raw, uncompromising speed of a native compiled systems language.

### 🚀 What makes it unique?
* **Zero-Cost Memory Management (No GC):** The compiler tracks the resource lifecycles (`Alive`, `HandedOver`, `InDebt`) across a customized Control Flow Graph (CFG) at compile time. No heavy garbage collector, no micro-stutters during animations.
* **UI Hierarchy as Lifetimes:** Instead of fighting complex lifetime annotations, Rose binds resource borrow spans directly to the layout tree structure (`Window -> Container -> Button`), making memory management invisible yet safe.
* **Native WebGPU Pipeline:** It bypasses heavy abstractions, batching layout nodes directly into GPU primitives via WGPU and raw WGSL shaders with strict `std140` buffer alignments.

### 📦 Current State: v0.0.7beta
The entire core toolchain is already operational! The `bud` CLI acts as a unified orchestrator—typing a single command like `bud run` fires up the Pratt parser, runs the dataflow memory audits, outputs bytecode, and spawns an interactive WGPU graphics window instantly.

I am releasing this pre-alpha beta to see if the community finds this concept as exciting as I do. If people like the idea, I would love for you to join me! The core engine is ready, but it needs help expanding the component registry, stress-testing the CFG borrow checker, and optimizing the layout math. 

Check out the code, grab the `roseup` installer, and let me know what you think! 🌹
