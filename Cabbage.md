---
layout: page
title: Cabbage Plugin
subtitle: Compilation and Installation
tags: [test]
comments: true
---
This is a guide I initially created in PowerPoint for my current customer and then moved to online documentation. Due to the NDA restrictions this is the only piece I can share.
## Prerequisites

First, you need to download the following software:
   NOTE: Install the software to the default directory.

- **Cabbage** [https://cabbageaudio.com](https://cabbageaudio.com)  
   > Free software for prototyping audio instruments with the Csound audio.
- **REAPER**  [https://www.reaper.fm](https://www.reaper.fm)  
   > A digital audio production application.
- **SPAN VST** [https://www.voxengo.com/product/span/](https://www.voxengo.com/product/span/)  
   > A free real-time FFT audio spectrum analyzer.
   For **SPAN VST** install only the selected components as shown below:
   ![SPAN setup](/assets/img/SPAN_setup.png)

## Plugin Compilation in Cabbage

1. Start _Cabbage_ from your PC's start menu.
2. Click **File** >**Open Csound file** to open a pre-created `spectra.сds` file.
3. Click **File** >**Export plugin**>**Export as VST Plugin Effect**.    
   - In **Save file as** dialog:
   > 1. Create a **VST** folder.
   > 2. Name the file, for example, `spectra.dll` and save it to the **VST** folder.
4. Close _Cabbage_.
5. Make sure the **VST** folder contains the two files:  
- [x] `.csd project file`  
- [x] `.dll library file`

## Plugin Intergration into REAPER

1. Open _REAPER_ from your desktop.
2. In **About REAPER** window, wait for the **Buy Me** button countdown before turning into **Still Evaluating**, and click it to use the application with the free Evaluation license.  
   ![REAPER license button](/assets/img/REAPER_license.png)

3. Specify audio device settings:Click **Options** tab>**Preferences** to access **REAPER Preferences**>**Device** and set:
   - **Audio system**: `ASIO`
   - **ASIO Driver**: `Roland Rubix`
4. In **REAPER Preferences** list scroll down and select **VST**. In **VST plug-ins settings** section:

   > 1. Click **Edit path list** button > **Add path** > navigate to add `Cabbage\VST directory`.
   > 2. Click **Edit path list button** > **Add path** > navigate to add path to SPAN (by default it is installed  to `C:\Program Files\Common Files\VST2\Voxengo)`.
   > 3. Click **Re-scan** button > select **Re-scan VST paths for new/modified plug-ins**.
   >   - After scanning click **OK** to close the **REAPER Preferences** dialog.
5. Click **File** > **Open project** > `spectra` (REAPER project file).
   - The program displays three windows: REAPER project, VST SPAN spectrum analyzer, and Cabbage plugin.

### Cabbage Plugin Window

In Cabbage plugin window update `VST:spectra` as the previous settings may be irrelevant/outdated:
1. Select`VST:spectra …` item.
2. Click **Remove** button.
3. Click **Add** button.
   - in **Add** dialog select **New** > `VST:spectra (Cabbage Audio)`, and click **Add**.  
4. Back in the Cabbage plugin window, drag `VST:spectra` up to make it the first item in the list.

   ![drag item up](/assets/img/Cabbage_drag.png)

#### Plugin Controls

**Noise Type** knob:  
> - type 0 – white noise
> - type 1 – pink noise
> - type 2 – brown noise

**Noise Level** knob:  
> Tunes the generated noise level in response to the vacuum cleaner output.

**MIX** knob:  
> Controls the level of effect.

<mark>Sorry, I need to stop here due to NDA restrictions</mark>
