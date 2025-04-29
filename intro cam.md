# Intro Camera Editing

Intro cameras are what you see as soon as the level is loaded. The little preview that shows you what the level is about\! First impressions are key and if your intro camera is the default flip swap pan forward camera that clips into a platform, you won't make a good impression. So that's where people usually do one of two things\! Either they delete the camera so it just starts instantly, or, what we're covering here, you make a custom one\! So let's get to that\!

## Prerequisites

* You'll need [WiiExplorer](https://github.com/SuperHackio/WiiExplorer) and [Launch Cam Plus](https://github.com/SuperHackio/LaunchCamPlus), by Super Hackio, and your levels *Map.arc* file.
* You *should* have [Whitehole Neo](https://github.com/SMGCommunity/Whitehole-Neo) to see coordinates for camera position (using a reference object).


### General tips and non-essential guidelines
<sub>*(How to make your camera make sense for your level)*</sub>

* Keep it simple \- you don't want 20 camera cuts in the 8 seconds (480 frames) the default camera length lasts, try and keep it to 2, *maybe* 3 cuts.  
* Remember the focus \- if your level is linear and has a set end location, it's always nice to have an intro camera end on the location of the star. For open world levels, maybe show the location of one of the objectives. For instance: if it is a silver star level, maybe give a subtle hint as to where one of the silver stars are.



## Preparations

To start, open your levels *Map.arc* file, then in the *camera* folder, extract the *StartScenario\#.canm* file. (\# being the number for the scenario that uses this camera). 

<p align="center" width="100%">
 <img src="images/intro_camera-GalaxyMapArcWiiExplorer.png">
 </p>

<p style="text-align: center;"><sub>Honeyhive Galaxy’s Map.arc file. (Please note that SMG1 has its internal files in lowercase. Capitalization doesn’t matter in SMG2, but in SMG1, files MUST be all lowercase.)</sub></p>

Then, open Launch Cam Plus, click File \> Open, then find the CANM you extracted. This will open the CANM editor.

<p align="center" width="100%">
 <img src="images/intro_camera-OpenScenarioStarter.gif">
 </p>



## Getting Started with CANM editing 

Opening the CANM file will present you with, well, quite a lot. But don’t worry, it’s a lot more simple than it looks. 

### Keyframe Types

<p align="center" width="100%">
 <img src="images/intro_camera-PosLCP.png">
 </p>

<p style="text-align: center;"><i>Position XYZ</i> is where the camera is <b><i>located</i></b> in the galaxy</p>

<p align="center" width="100%">
 <img src="images/intro_camera-TargetLCP.png">
 </p>

<p style="text-align: center;"><i>Target XYZ</i> is where the camera is <b><i>looking</i></b> in the galaxy</p>

<p align="center" width="100%">
 <img src="images/intro_camera-RollLCP.png">
 </p>

<p style="text-align: center;"><i>Roll</i> is the <b><i>Rotation</i></b> of the camera. From -180 to 180. Either -180 or 180 is upside down. 0 is straight up.</p>

<p align="center" width="100%">
 <img src="images/intro_camera-LCP-FOV.png">
 </p>

<p style="text-align: center;">And finally, <i>Field of View (or FOV)</i> is how <b><i>zoomed in</i></b> the camera is.</p>

### Coordinates

Coordinates in a galaxy can be easily found by placing a reference object in your level. Here, I’ll be using a coin, so when I mention the coin, I mean whatever object you use as a reference.

Say you want to make a simple intro camera. The camera moves from point A to B (red) while looking at point C (green) which does not move.

<p align="center" width="100%">
 <img src="images/intro_camera-ExampleDiagram.png">
 </p>

I have already placed coins in these positions, as you can see, and will use the positions of those coins (visible in Whitehole) as keyframe points. This camera will only use 2 keyframes for each `Position` axis and one keyframe for each `Target` axis.

---

### Make sure your reference objects are in the <u>___MAIN GALAXY___</u>, not the zone!
<p align="center" width="100%">
 <img src="images/intro_camera-Correct-In-Galaxy.png">
 </p>

`HoneyBeeKingdomGalaxy`✅

<p align="center" width="100%">
 <img src="images/intro_camera-Incorrect-In-Zone.png">
 </p>

`ForestHomeZone`❌

---

Now, this might be confusing, so I'll try and make this as simple to understand as possible.

First, let's set up the keyframes. It'll be easier if we set these up first, trust me.

Starting off, for a simple point A to B camera, you'll want to make 2 camera keyframes for each `Position` and (if its only looking at one spot), one for the `Target` entry. Under `Keyframe Data` you can enter the frame number in the `Time` slot.

If you're opening a CANM file from the base game, you'll see a lot of keyframes. You'll probably want to delete most of the existing ones. Especially for a simple camera such as the one we're making here.

<p align="center" width="100%">
 <img src="images/intro_camera-Before.png">
 </p>
<p style="text-align: center;">Before</p>

---

 <p align="center" width="100%">
 <img src="images/intro_camera-After.png">
 </p> 
<p style="text-align: center;">After</p>

<sub>(Tip, you can press CTRL + A to create a new keyframe, and CTRL + DEL to delete the currently highlighted keyframe.)</sub>

Next, look at the position of Coin A.

<p align="center" width="100%">
 <img src="images/intro_camera-CoinAPos.png">
 </p>

Take note of these coordinates. Then, in LaunchCamPlus, take the X, Y, and Z positions from Coin A, and put them in the corresponding `Position` sections first frames.

Then, do the same with Coin B in the final frames of `Position`.

<p align="center" width="100%">
 <img src="images/intro_camera-CoinBPos.png">
 </p>

They should look like this, see the coordinates above, and how they correlate to the `Value` section in `Keyframe Data` in this GIF.

<p align="center" width="100%">
 <img src="images/intro_camera-PositionXYZ-LCP.gif">
 </p>

Now, the `Target` position. This one is simpler, as in this instance, it doesn't move.

Here are the position coordinates for Coin C

<p align="center" width="100%">
 <img src="images/intro_camera-CoinCPos.png">
 </p>

Now here are the same coordinates in the `Target` section of LCP

<p align="center" width="100%">
 <img src="images/intro_camera-TargetXYZ-LCP.gif">
 </p>

And we're done! Here's how the final camera looks!

<p align="center" width="100%">
 <img src="images/intro_camera-final-camera!!.gif">
 </p>

Pretty simple, but that's all that this guide is for! This guide is just covering how to use this part of the program. It is up to you to mess around with the program and make something suitable for your level.

## Examples

### *Roll:* 0 to -180
<p align="center" width="100%">
 <img src="images/intro_camera-rolling-from-0-to-positive-180.gif">
 </p>
<p align="center" width="100%">
 <img src="images/intro_camera-roll-negative-example.png">
 </p>

### *Roll:* 0 to +180
<p align="center" width="100%">
 <img src="images/intro_camera-rolling-from-0-to--180.gif">
 </p>
<p align="center" width="100%">
 <img src="images/intro_camera-roll-positive-example.png">
 </p>

### *Field of View:* 0 to 90
<p align="center" width="100%">
 <img src="images/intro_camera-FOV 0 to 90.gif">
 </p>
 <p align="center" width="100%">
 <img src="images/intro_camera-fovexample.png">
 </p>

## Jump cuts

To make a jump cut, have where you want the camera to be on one frame, then the NEXT frame, set where you want the camera to cut to. (A purple line in LCP indicates a jump cut)

<p align="center" width="100%">
 <img src="images/intro_camera-jumpcut.png">
 </p>
<p align="center" width="100%">
 <img src="images/intro_camera-jumpcut2.png">
 </p>

## Final note

The best way to learn how to do these more is just to experiment with them! I hope this guide helped you figure out how the CANM editor works, and that it helps you make some awesome looking intro cameras!

---

*Written by Syreyup*
