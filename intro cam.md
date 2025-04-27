# Intro Camera Editing

Intro cameras are what you see as soon as the level is loaded. The little preview that shows you what the level is about\! First impressions are key and if your intro camera is the default flip swap pan forward camera that clips into a platform, you won't make a good impression. So that's where people usually do one of two things\! Either they delete the camera so it just starts instantly, or, what we're covering here, you make a custom one\! So let's get to that\!

### Prerequisites

* You'll need [WiiExplorer](https://github.com/SuperHackio/WiiExplorer) and [Launch Cam Plus](https://github.com/SuperHackio/LaunchCamPlus), by Super Hackio, and your levels *Map.arc* file.
* You *should* have [Whitehole Neo](https://github.com/SMGCommunity/Whitehole-Neo) to see coordinates for camera position (using a reference object).

### General tips and non-essential guidelines
*(How to make your camera make sense for your level)*

* Keep it simple \- you don't want 20 camera cuts in the 8 seconds (480 frames) the default camera length lasts, try and keep it to 2, *maybe* 3 cuts.  
* Remember the focus \- if your level is linear and has a set end location, it's always nice to have an intro camera end on the location of the star. For open world levels, maybe show the location of one of the objectives. Like if it's a silver star level, maybe give a subtle hint as to where one of the silver stars are.



## Preparations

To start, open your levels *Map.arc* file, then in the *camera* folder, extract the *StartScenario\#.canm* file. (\# being the number for the scenario that uses this camera). 

![WiiExplorer_pMQIMVOD7B](https://github.com/user-attachments/assets/3a0d6e39-9d6c-4720-9cab-4b5899406cd8)

<sup>Honeyhive Galaxy’s Map.arc file. (Please note that SMG1 has its internal files in lowercase. Capitalization doesn’t matter in SMG2, but in SMG1, files MUST be all lowercase.)<sup>

Then, open Launch Cam Plus, click File \> Open, then find the CANM you extracted. This will open the CANM editor.
![LaunchCamPlus_T5tTBQXTnh](https://github.com/user-attachments/assets/69d7d930-8b8e-4a0e-ac31-2bd759685a8f)



## Getting Started with CANM editing 

Opening the CANM file will present you with, well, quite a lot. But don’t worry, it’s a lot more simple than it looks. 

### Keyframe Types


![LaunchCamPlus_YB0U1sJXPL](https://github.com/user-attachments/assets/3c617638-54db-4bbd-a6ec-bfc5fff3ac0b)
*Position XYZ* is where the camera is ***Located*** in the galaxy

![LaunchCamPlus_w90oo5wdl3](https://github.com/user-attachments/assets/6df330e0-5d90-4c27-a5a6-e232d30b26c1)
*Target XYZ* is where the camera is ***Looking*** in the galaxy

![LaunchCamPlus_HKJ1ZSmOLg](https://github.com/user-attachments/assets/9f37b426-9c9c-4b6f-bf63-4383c50dc1aa)
*Roll* is the ***Rotation*** of the camera. From \-180 to 180\. Either \-180 or 180 is exactly upside down. 0 is straight up.   

![LaunchCamPlus_eDQZOqcPfx](https://github.com/user-attachments/assets/8c2ee47e-2367-42d2-afdd-cea24818908c)
And finally, *Field of View* *(or FOV)* is how ***zoomed in*** the camera is.

### Coordinates

Coordinates in a galaxy can be easily found by placing a reference object in your level. Here, I’ll be using a coin.

## Examples:

#### *Roll:* 0 to NEGATIVE 180

![0 to NEGATIVE_180](https://github.com/Syreyup/markdownviewer/blob/main/images/rolling%20from%200%20to%20-180.gif)

#### *Roll:* 0 to POSITIVE 180

![0_to_POSITIVE_180](https://github.com/Syreyup/markdownviewer/blob/main/images/rolling%20from%200%20to%20positive%20180.gif)

#### *Field of View:* 0 to 90

![FOV_0_to_90](https://github.com/Syreyup/markdownviewer/blob/main/images/r%20FOV%200%20to%2090.gif?)

*Written by Syreyup*
