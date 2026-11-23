<div align="center">

# FND Reverb

[Product and research values](#product-and-research-values)

**A VST3 and standalone reverb effect by Stancsz Audio**

[![Releases](https://img.shields.io/github/v/release/stancsz/fnd-reverb-vst3?label=release)](https://github.com/stancsz/fnd-reverb-vst3/releases)

</div>

![FND Reverb interface](docs/screenshot.png)

FND Reverb provides named sound modes and a parameterized effect chain for creative reverb shaping. The current processor uses the JUCE DSP reverb core and applies additional shaping stages. Its mode names are parameter mappings for a shared core, not twenty-one independent algorithms or a custom feedback-delay network.

## Product and research values

- **Creative control:** provide approachable, recallable settings for shaping reverb.
- **Accurate signal-flow claims:** JUCE DSP supplies the reverb core; the repository does not implement a custom FDN.
- **Measured quality:** no latency, high-fidelity, or acoustic-superiority claim is made without controlled measurement and listening.
- **License clarity:** this repository currently has no root license resolving the complete plugin-source distribution. Review JUCE and dependency terms before redistribution or describing the project as open source.

## Processing overview

The processor maps feedback, density, and width controls into JUCE reverb parameters, with per-mode adjustments. It also includes predelay, chorus, saturation, filtering, a three-band EQ, dynamic EQ, gate/ducking behavior, wet/dry handling, and an optional output limiter. This overview is source-grounded; the exact chain and behavior may change with future commits.

## Build

Prerequisites: CMake 3.15 or newer and a C++17 compiler. CMake fetches JUCE 8.0.4 when it is not already available.

**Windows**

    cmake -B build -S .
    cmake --build build --config Release

The VST3 and standalone outputs are under the FDNR_artefacts directory; the exact configuration subdirectory depends on the CMake generator. In a DAW, install the VST3 bundle in a scanned VST3 directory and rescan plugins.

Linux builds additionally require ALSA and GTK 3 development packages. The repository has not published cross-platform compatibility evidence.

## References

- [JUCE DSP Reverb documentation](https://docs.juce.com/master/classjuce_1_1dsp_1_1Reverb.html)
- [Releases](https://github.com/stancsz/fnd-reverb-vst3/releases)
