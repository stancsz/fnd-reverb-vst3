# A Parameterized Reverb Effect Plugin Built on JUCE DSP

Implementation notes and an evaluation plan for FND Reverb VST3

## Abstract

This engineering report documents FND Reverb VST3 as a parameterized audio effect built around the JUCE DSP reverb core. The source combines named mode mappings with a shared reverb and additional stages such as predelay, chorus, saturation, filtering, dynamic processing, stereo controls, and output limiting. Mode names and mappings do not constitute twenty-one independently implemented reverberation algorithms or a custom feedback-delay network. No acoustic benchmark, blinded listening test, latency characterization, or comparative plugin study is reported. This draft provides a source-grounded description and a reproducible evaluation plan. Distribution and source licensing require a separate explicit review.

## 1. Scope and motivation

A large set of preset or mode labels does not explain the underlying signal processing. This report describes the implementation visible in the repository and distinguishes named configurations from DSP architecture.

Processor source confirms the JUCE DSP reverb core and its parameter mappings [R3]. JUCE documents a simple stereo core based on FreeVerb techniques [R1]; an open FreeVerb implementation is described in [R2]. The current implementation should be described as a JUCE-core effect chain, not as a newly proposed FDN.

## 2. Signal path and evidence

The processor maps controls into room-size, damping, and width parameters, applies mode-specific adjustments, and owns additional delay, chorus, filtering, equalization, saturation, and limiting stages. The precise order and bypass behavior should be checked against source for each release.

No latency, acoustic-superiority, or high-fidelity result is reported. A technical study should publish parameter mappings and test impulse responses, decay, frequency-dependent decay, stereo correlation, peak level, latency, and sample-rate behavior.

## Product and research values

The product goal is an approachable set of reverb sounds with recallable settings. Branding and mode labels should promise only what the processor implements.

- **Creative control:** approachable settings for shaping and recalling reverb.
- **Accurate signal-flow claims:** JUCE DSP supplies the reverb core.
- **Measured quality:** no latency or acoustic superiority claim without controlled measurement and listening.
- **License clarity:** no root license resolves the complete source distribution; review JUCE and dependency terms before redistribution.

## 3. Limitations and future work

The repository currently has no root license file resolving the complete plugin-source distribution. JUCE terms and all dependencies must be reviewed before claiming open-source status or commercial redistribution rights.

No VST3 build or screenshot establishes audio quality, compatibility, or readiness. Compare the shared JUCE core against added stages under matched settings, and publish raw captures and measurement methods.

## 4. Conclusion

FND Reverb VST3 is best described as a JUCE DSP reverb core surrounded by a parameterized effect chain. Acoustic and listening evidence remains to be collected.

## References

[R1] JUCE. juce::dsp::Reverb class documentation. URL: https://docs.juce.com/master/classjuce_1_1dsp_1_1Reverb.html
[R2] Jezar at Dreampoint. Freeverb implementation. URL: https://github.com/sinshu/freeverb
[R3] Chen, S. FND Reverb VST3 repository. URL: https://github.com/stancsz/fnd-reverb-vst3