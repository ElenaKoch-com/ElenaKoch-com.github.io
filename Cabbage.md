---
layout: page
title: Cabbage Plugin
subtitle: Compilation and Installation
tags: [test]
comments: true
---
This guide explains how to install, compile, and integrate audio software to visualize the generated sound effect in real time.

## Prerequisites

Download the following software from the official websites to your default directory:
- **Cabbage** [https://cabbageaudio.com](https://cabbageaudio.com)  
   > Free software for prototyping audio instruments with the Csound audio.  
- **REAPER**  [https://www.reaper.fm](https://www.reaper.fm)  
   > A digital audio production application.
- **SPAN VST** [https://www.voxengo.com/product/span/](https://www.voxengo.com/product/span/)  
   > A free real-time FFT audio spectrum analyzer.

For **SPAN VST**, install only the selected components as shown below:
![SPAN setup](/assets/img/SPAN_setup.png)

## Plugin Compilation in Cabbage

1. Launch _Cabbage_ from the Windows Start menu. 
2. Open a pre-created `spectra.сds` file: **File** > **Open Csound file**. 
3. Click **File** > **Export plugin** > **Export as VST Plugin Effect**.    
   - In **Save file as** dialog:      
    1. Create a **VST** folder.  
    2. Name the file, for example, `spectra.dll` and save it to the **VST** folder.
7. Close _Cabbage_.
8. Make sure the **VST** folder contains the two files:  
   - [x] `.csd project file`  
   - [x] `.dll library file`

## Plugin Integration into REAPER

1. Launch _REAPER_ on your desktop.
2. To use the application with the free Evaluation license, do the following in the **About REAPER** window:
   - Notice that the **Buy Me** button displays Days Left countdown. 
   - Wait for the button text to change to **Still Evaluating** and click it.
   
   ![REAPER license button](/assets/img/REAPER_license.png)

3. Specify audio device settings in the **Options** tab > **Preferences**:  
   1. Select **REAPER Preferences** > **Device**:
      - **Audio system**: _ASIO_
      - **ASIO Driver**: _Roland Rubix_ 
   2. In the **REAPER Preferences** list scroll down and select **VST**.
   3. In the **VST plug-ins settings** section:
      1. Click the **Edit path list** button > **Add path** > navigate to add `Cabbage\VST directory`.
      2. Click the **Edit path list** button > **Add path** > navigate to add path to SPAN   
          - default installation directory is `C:\Program Files\Common Files\VST2\Voxengo`.
      4. Click the **Re-scan** button > select **Re-scan VST paths for new/modified plug-ins**.
      5. After scanning, click **OK** to close the **REAPER Preferences** dialog.
4. Click **File** > **Open project** > `spectra` (REAPER project file).
5. The program displays three windows:  
    - REAPER project
    - VST SPAN spectrum analyzer
    - Cabbage plugin

### Cabbage Plugin Window

To update `VST:spectra` in the Cabbage plugin window:
1. Select the `VST:spectra …` item.
2. Click the **Remove** button to delete the previous settings that may be irrelevant/outdated.
3. Click the **Add** button.
   - in the **Add** dialog select **New** > `VST:spectra (Cabbage Audio)`, and click **Add**.  
4. Back in the Cabbage plugin window, drag `VST:spectra` up to make it the first item in the list:

   ![drag item up](/assets/img/Cabbage_drag.png)

#### Plugin Controls

**Noise Type** knob   
> - type 0 – white noise
> - type 1 – pink noise
> - type 2 – brown noise

**Noise Level** knob   
> tunes the generated noise level in response to the device's output.

**MIX** knob   
> controls the level of effect.

<mark>Sorry, I need to stop here due to NDA restrictions</mark>
