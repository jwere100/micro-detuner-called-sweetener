# Sweetener
One of main obstacles many amateurs face in the mixing stage is the lack of "variance" or "feel" in a track. Digital audio, especially in home-studio workflows, often sounds static, overly clean, and harmonically "flat". If you've ever watched a professional mixer or engineer work, you'll seem them utilize industry-grade plugins, which include spectral exciters, shapers, saturators, etc. These plugins contain underlying modifiers that create difference in tone, enhance harmonics, and introduce micro-movements into the audio. This often leads many engineers to describe certain plugins to have a certain effect or sound, such as "gluing" the vocals to the track or "lifting" the vocals up. Without these micro-variations, a mix doesn’t feel “finished" or "professional". Often times, this phenomena is what seperates an amateurs mix from a professional mix.

**Sweetener** is inteded to be a lightweight, open-source tool designed to recreate a key partof a professional "feel". Sweetener applies micro-detuning and phase perturbation (explained later) only to the upper harominc bands of a signal. This adds a sense feeling of shimmer to the mix, which can be equivocated to "lifting" up the mid-range elements of a song (including vocals).

Hold up, looks like amateur Johnny has a question:
**Why not just boost the highs with an eq?**
Eq boosting results in making the existing mid-to-high frequency content louder, not better. If the top end is already static and lifeless, an EQ would simply amplify that lifelessness. In constrast, Sweetener does not increase the treble volume at all; it increases the quality by adding variations and phase shifts at intended frequencies. 

### Installation Guide
Sweetener can be built either as a JUCE Plugin or a standalone CLI (WAV -> WAV) tool.

### First Option: Juce Plugin
**Requirements**
- CMAKE 3.20+
- A C++17 compiler
- Xcode Command Line Tools OR Windows Visual Studio 2022
- JUCE (added as a submodule or provided locally)

#### Clone
`
git clone https://github.com/<your-username>/micro-detuner-called-sweetener.git
cd micro-detuner-called-sweetener
`
#### Get JUCE
`
git submodule update --init --recursive
`
#### Build
`
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release
`
If your DAW doesn't see the plugin, rescan plugin folders.
### Second Option (Faster): CLI
This builds a simple command-line program that processes a WAV file and writes the result.
#### Build
`
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release -DSWEETENER_BUILD_CLI=ON
cmake --build build --config Release
`
Run
`
./build/sweetener_cli input.wav output.wav --wet 0.25 --cutoff 4000 --phase 0.01 --width 0.7
`

### Troubleshooting
- Run
`
git submodule update --init --recursive
`
- Check plugin folder
- Audio sounds weird: Lower --phase, --wet, or raise --cutoff
Otherwise, ask ChatGPT, I don't know


`
