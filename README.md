# Low Quality

A Geode mod for Geometry Dash that adds quality presets to reduce screen resolution, FPS, and audio quality on Android and PC.

## Presets

| Preset | Scale | FPS cap | Audio |
|--------|-------|---------|-------|
| Normal | 100% | Unchanged | Unchanged |
| low | 93% | Unchanged | Normal |
| lower | 82% | 45 | Normal |
| trash | 68% | 30 | Normal |
| 8k 120 FPS | 45% | 12 | Degraded |

## Building

This project uses **GitHub Actions** for cloud compilation. Push to any branch and the workflow will automatically build the mod for all platforms.

### Platforms built
- Windows (`openai.low-quality.windows.dll`)
- Android ARM32 (`openai.low-quality.android32.so`)
- Android ARM64 (`openai.low-quality.android64.so`)
- macOS (`openai.low-quality.mac.dylib`)

The compiled `.geode` package will appear as a workflow artifact in the **Actions** tab.

### Local build

Prerequisites: [Geode SDK](https://docs.geode-sdk.org/getting-started/create-mod), CMake ≥ 3.21, a C++20-capable compiler.

```sh
cmake -B build
cmake --build build
```