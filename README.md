Hello everyone! 

I want to share an experimental project I’ve been building as a passionate hobby: **Rose (RoseScript Canvas)**, a statically-typed declarative UI language designed for ultra-lightweight, hardware-accelerated desktop interfaces. 

I’ll be honest with you: I’m not a programmer at all. I wrote all of this with the help of AI, so I don’t know how you’ll react to it. This project is just a hobby—I’ve only been working on it for a month—but I’ve enjoyed it so much that I really want it to become popular. I realize there aren't any libraries for it and that it might not be grabbing much of your attention... But again, I’m not a programmer; I don’t see things the way you do... :(

### 🚀 What makes it unique?
* **Zero-Cost Memory Management (No GC):** The compiler tracks the resource lifecycles (`Alive`, `HandedOver`, `InDebt`) across a customized Control Flow Graph (CFG) at compile time. No heavy garbage collector, no micro-stutters during animations.
* **UI Hierarchy as Lifetimes:** Instead of fighting complex lifetime annotations, Rose binds resource borrow spans directly to the layout tree structure (`Window -> Container -> Button`), making memory management invisible yet safe.
* **Native WebGPU Pipeline:** It bypasses heavy abstractions, batching layout nodes directly into GPU primitives via WGPU and raw WGSL shaders with strict `std140` buffer alignments.

### 📦 Current State: v0.0.7beta
The entire core toolchain is already operational! The `bud` CLI acts as a unified orchestrator—typing a single command like `bud run` fires up the Pratt parser, runs the dataflow memory audits, outputs bytecode, and spawns an interactive WGPU graphics window instantly.

I am releasing this pre-alpha beta to see if the community finds this concept as exciting as I do. If people like the idea, I would love for you to join me! The core engine is ready, but it needs help expanding the component registry, stress-testing the CFG borrow checker, and optimizing the layout math. 

Check out the code, grab the `roseup` installer, and let me know what you think! 🌹
