# Sweetener
One of main obstacles many amateurs face in the mixing stage is the lack of "variance" or "feel" in a track. Digital audio, especially in home-studio workflows, often sounds static, overly clean, and harmonically "flat". If you've ever watched a professional mixer or engineer work, you'll seem them utilize industry-grade plugins, which include spectral exciters, shapers, saturators, etc. These plugins contain underlying modifiers that create difference in tone, enhance harmonics, and introduce micro-movements into the audio. This often leads many engineers to describe certain plugins to have a certain effect or sound, such as "gluing" the vocals to the track or "lifting" the vocals up. Without these micro-variations, a mix doesn’t feel “finished" or "professional". Often times, this phenomena is what seperates an amateurs mix from a professional mix.

**Sweetener** is inteded to be a lightweight, open-source tool designed to recreate a key partof a professional "feel". Sweetener applies micro-detuning and phase perturbation (explained later) only to the upper harominc bands of a signal. This adds a sense feeling of shimmer to the mix, which can be equivocated to "lifting" up the mid-range elements of a song (including vocals).

Hold up, looks like amateur Johnny has a question:
**Why not just boost the highs with an eq?**
Eq boosting results in making the existing mid-to-high frequency content louder, not better. If the top end is already static and lifeless, an EQ would simply amplify that lifelessness. In constrast, Sweetener does not increase the treble volume at all; it increases the quality by adding variations and phase shifts at intended frequencies. 

#Supported Environments


