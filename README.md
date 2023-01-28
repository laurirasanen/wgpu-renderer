# wpgu-renderer

A small [wgpu](https://github.com/gfx-rs/wgpu) renderer written in [Rust](https://github.com/rust-lang/rust).

## Try it out
[rasanen.dev/wgpu-renderer](https://rasanen.dev/wgpu-renderer)  
Note: the .wasm is about 50 MB because it embeds Sponza.

Controls:
- WASD - Move horizontally
- Ctrl/Space - Move vertically
- Mouse - Look around
- Scrollwheel - Increase/Decrease movement speed
- ESC - Quit (Only on standalone version)

## Features

- Physically based shading
  - (F: Fresnel-Schlick approximation)
  - (G: Smith's Schlick-GGX)
  - (D: Trowbridge-Reitz GGX)
- glTF models
- 1 realtime pointlight
- Simple wgsl preprocessor for includes
- Runs on WASM and native desktop

TODO:
- Shadow mapping
- Restructuring
    - Simplify/abstract renderpasses; will be nice to have for PP and GI
    - `src/core/state.rs` is a mess; separate input handling, pipeline, passes
- SSAO
- Bloom
- AA
- Texture filtering
- Immediate mode UI (dear imgui, egui)
- Some type of GI (DDGI, VXGI)

## Running locally

Standalone:
```sh
cargo run --release
```

WASM requires [miniserve](https://github.com/svenstaro/miniserve), or some other http server, such as `python3 -m http.server`.  
For miniserve, see:
```sh
./run-wasm.sh
```

## References
- [wgpu examples](https://github.com/gfx-rs/wgpu/blob/master/wgpu/examples)
- [Learn Wgpu](https://sotrh.github.io/learn-wgpu/)
- [Learn OpenGL: PBR](https://learnopengl.com/PBR/Theory)

## Assets
- Sponza
  - Obtained from [KhronosGroup glTF-Sample-Models repository](https://github.com/KhronosGroup/glTF-Sample-Models/tree/16e2408d31e06d4b0bcf6123db472e802d71f081/2.0/Sponza), converted to .glb
