# Intro Camera Editing

Intro cameras are what you see as soon as the level is loaded. The little preview that shows you what the level is about\! First impressions are key and if your intro camera is the default flip swap pan forward camera that clips into a platform, you won't make a good impression. So that's where people usually do one of two things\! Either they delete the camera so it just starts instantly, or, what we're covering here, you make a custom one\! So let's get to that\!

## Prerequisites

* You'll need [WiiExplorer](https://github.com/SuperHackio/WiiExplorer) and [Launch Cam Plus](https://github.com/SuperHackio/LaunchCamPlus), by Super Hackio, and your levels *Map.arc* file.
* You *should* have [Whitehole Neo](https://github.com/SMGCommunity/Whitehole-Neo) to see coordinates for camera position (using a reference object).


### General tips and non-essential guidelines
##### *(How to make your camera make sense for your level)*

* Keep it simple \- you don't want 20 camera cuts in the 8 seconds (480 frames) the default camera length lasts, try and keep it to 2, *maybe* 3 cuts.  
* Remember the focus \- if your level is linear and has a set end location, it's always nice to have an intro camera end on the location of the star. For open world levels, maybe show the location of one of the objectives. Like if it's a silver star level, maybe give a subtle hint as to where one of the silver stars are.



## Preparations

To start, open your levels *Map.arc* file, then in the *camera* folder, extract the *StartScenario\#.canm* file. (\# being the number for the scenario that uses this camera). 

<p align="center" width="100%">
 <img src="images/WiiExplorer_pMQIMVOD7B.png">
 </p>

##### Honeyhive Galaxy’s Map.arc file. (Please note that SMG1 has its internal files in lowercase. Capitalization doesn’t matter in SMG2, but in SMG1, files MUST be all lowercase.)

Then, open Launch Cam Plus, click File \> Open, then find the CANM you extracted. This will open the CANM editor.
<p align="left" width="100%">
 <img src="images/LaunchCamPlus_T5tTBQXTnh.gif">
 </p>



## Getting Started with CANM editing 

Opening the CANM file will present you with, well, quite a lot. But don’t worry, it’s a lot more simple than it looks. 

### Keyframe Types

<p align="left" width="100%">
 <img src="images/PosLCP.png">
 </p>

*Position XYZ* is where the camera is ***located*** in the galaxy

<p align="left" width="100%">
 <img src="images/TargetLCP.png">
 </p>

*Target XYZ* is where the camera is ***looking*** in the galaxy

<p align="left" width="100%">
 <img src="images/RollLCP.png">
 </p>

*Roll* is the ***Rotation*** of the camera. From \-180 to 180\. Either \-180 or 180 is exactly upside down. 0 is straight up.   

<p align="left" width="100%">
 <img src="images/LCP-FOV.png">
 </p>

And finally, *Field of View* *(or FOV)* is how ***zoomed in*** the camera is.

### Coordinates

Coordinates in a galaxy can be easily found by placing a reference object in your level. Here, I’ll be using a coin, so when I mention the coin, I mean whatever object you use as a reference.

Say you want to make a simple intro camera. The camera moves from point A to B (red) while looking at point C (green) which does not move.

<p align="center" width="100%">
 <img src="images/example.png">
 </p>

I have already placed coins in these positions, as you can see, and will use the positions of those coins (visible in Whitehole) as keyframe points. This camera will only use 2 time keyframes. 

---

### Make sure your reference objects are in the <u>___MAIN GALAXY___</u>, not the zone!
<p width="100%">
 <img src="images/java_0pqVM1ZEZH.png">
 </p>

`HoneyBeeKingdomGalaxy`✅

<p width="100%">
 <img src="images/java_zaM4kiYbIQ.png">
 </p>

`ForestHomeZone`❌

---

Now, this might be confusing, so I'll try and go through this as step-by-step as possible.

First, let's set up the keyframes. It'll be easier if we set these up first, trust me.

Starting off, for a simple Point A to B camera, you'll want to make 2 camera timing points for each Position and Target entry. Under `Keyframe Data` you can enter the frame number in the `Time` slot.

If you're opening a CANM file from the base game, you'll see a lot of timing points. You'll probably want to delete most of the existing ones. Especially for a simple camera such as the one we're making here.

<p align="left" width="100%">
 <img src="images/LaunchCamPlus_0qqYjjrO6T.png"> Before
 </p>
 
 <p align="left" width="100%">
 <img src="images/LaunchCamPlus_NL6GmtUWeI.png"> After
 </p> 

##### (Tip, you can press CTRL + A to create a new timing point, and CTRL + DEL to delete the currently highlighted timing point.)

Next, look at the position of Coin A.

<p align="left" width="100%">
 <img src="images/java_KM3890ay11.png">
 </p>

Take note of these coordinates. Then, in LaunchCamPlus, take the X, Y, and Z positions from Coin A, and put them in the corresponding `Position` sections first frames.

Then, do the same with Coin B in the final frames of `Position`.

<p align="left" width="100%">
 <img src="images/dK8wNZ9LLs.png">
 </p>

They should look like this, see the coordinates above, and how they correlate to the `Value` section in `Keyframe Data` in this GIF.

<p align="center" width="100%">
 <img src="images/LaunchCamPlus_lon5veDrw5.gif">
 </p>

Now, the `Target` position. This one is simpler, as in this instance, it doesn't move.

Here are the position coordinates for Coin C

<p align="left" width="100%">
 <img src="images/java_UXNHHY6Zdi.png">
 </p>

Now here are the same coordinates in the `Target` section of LCP

<p align="center" width="100%">
 <img src="images/LaunchCamPlus_cm4Pb7w4PF.gif">
 </p>

And we're done! Here's how the final camera looks!

<p align="center" width="100%">
 <img src="images/final camera!!.gif">
 </p>

Pretty simple, but that's all that this guide is for! This guide is just covering how to use this part of the program. It is up to you to mess around with the program and make something suitable for your level. 

## Examples

### *Roll:* 0 to -180
<p align="center" width="100%">
 <img src="images/rolling from 0 to positive 180.gif">
 </p>

### *Roll:* 0 to +180
<p align="center" width="100%">
 <img src="images/rolling from 0 to -180.gif">
 </p>

### *Field of View:* 0 to 90
<p align="center" width="100%">
 <img src="images/r FOV 0 to 90.gif">
 </p>

## Final note

The best way to learn how to do these more is just to experiment with them! I hope this guide helped you figure out how the CANM editor works, and that it helps you make some awesome looking intro cameras! 

---

*Written by Syreyup*