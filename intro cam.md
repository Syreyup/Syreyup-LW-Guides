# Intro Camera Editing

Intro cameras are what you see as soon as the level is loaded. The little preview that shows you what the level is about\! First impressions are key and if your intro camera is the default flip swap pan forward camera that clips into a platform, you won't make a good impression. So that's where people usually do one of two things\! Either they delete the camera so it just starts instantly, or, what we're covering here, you make a custom one\! So let's get to that\!

## Prerequisites

* You'll need [WiiExplorer](https://github.com/SuperHackio/WiiExplorer) and [Launch Cam Plus](https://github.com/SuperHackio/LaunchCamPlus), by Super Hackio, and your levels *Map.arc* file.
* You *should* have [Whitehole Neo](https://github.com/SMGCommunity/Whitehole-Neo) to see coordinates for camera position (using a reference object).

### General tips and non-essential guidelines
*(How to make your camera make sense for your level)*

* Keep it simple \- you don't want 20 camera cuts in the 8 seconds (480 frames) the default camera length lasts, try and keep it to 2, *maybe* 3 cuts.  
* Remember the focus \- if your level is linear and has a set end location, it's always nice to have an intro camera end on the location of the star. For open world levels, maybe show the location of one of the objectives. Like if it's a silver star level, maybe give a subtle hint as to where one of the silver stars are.



## Preparations

To start, open your levels *Map.arc* file, then in the *camera* folder, extract the *StartScenario\#.canm* file. (\# being the number for the scenario that uses this camera). 

![WiiExplorer_pMQIMVOD7B](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437884716-3a0d6e39-9d6c-4720-9cab-4b5899406cd8.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075607Z&X-Amz-Expires=300&X-Amz-Signature=a3e92eec9e3eb2dab61567d8402c9faaf71b187fec7339cf5c6f2ac0fe6ac1e1&X-Amz-SignedHeaders=host)

<sup>Honeyhive Galaxy’s Map.arc file. (Please note that SMG1 has its internal files in lowercase. Capitalization doesn’t matter in SMG2, but in SMG1, files MUST be all lowercase.)<sup>

Then, open Launch Cam Plus, click File \> Open, then find the CANM you extracted. This will open the CANM editor.
![LaunchCamPlus_T5tTBQXTnh](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437885200-69d7d930-8b8e-4a0e-ac31-2bd759685a8f.gif?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075559Z&X-Amz-Expires=300&X-Amz-Signature=afd27f110cb7e6c85f159db46a0d43cd4f486a5eb7ca5aea7032ed423c16a12d&X-Amz-SignedHeaders=host)



## Getting Started with CANM editing 

Opening the CANM file will present you with, well, quite a lot. But don’t worry, it’s a lot more simple than it looks. 

### Keyframe Types


![PositionLCP](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437891640-3c617638-54db-4bbd-a6ec-bfc5fff3ac0b.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075348Z&X-Amz-Expires=300&X-Amz-Signature=93258948f18b59ef6c951a152dd81a3c9076302d594ac1332defbc8d50ed39f2&X-Amz-SignedHeaders=host)
*Position XYZ* is where the camera is ***located*** in the galaxy

![TargetLCP](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437891797-6df330e0-5d90-4c27-a5a6-e232d30b26c1.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075454Z&X-Amz-Expires=300&X-Amz-Signature=52ab54925365e4251bf3c2a09085cd51dc448ccc7b87137f1793a79d8f6f9880&X-Amz-SignedHeaders=host)
*Target XYZ* is where the camera is ***looking*** in the galaxy

![RotationLCP](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437892117-9f37b426-9c9c-4b6f-bf63-4383c50dc1aa.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075347Z&X-Amz-Expires=300&X-Amz-Signature=04a9fa65034620f4af4970504448971b69220a02b2db2ee0b02f056ccd4f961e&X-Amz-SignedHeaders=host)
*Roll* is the ***Rotation*** of the camera. From \-180 to 180\. Either \-180 or 180 is exactly upside down. 0 is straight up.   

![FieldOfViewLCP](https://github-production-user-asset-6210df.s3.amazonaws.com/89299730/437892226-8c2ee47e-2367-42d2-afdd-cea24818908c.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250427%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250427T075346Z&X-Amz-Expires=300&X-Amz-Signature=e897c42487a18ba2640538ceb3045e6f447026c84aa9ba538eb867363961b350&X-Amz-SignedHeaders=host)
And finally, *Field of View* *(or FOV)* is how ***zoomed in*** the camera is.

### Coordinates

Coordinates in a galaxy can be easily found by placing a reference object in your level. Here, I’ll be using a coin, so when I mention the coin, I mean whatever object you use as a reference.

Say you want to make a simple intro camera. The camera moves from point A to B (red) while looking at point C (green) which does not move.

![PointABC-Example](images/example.png)

I have already placed coins in these positions, as you can see, and will use the positions of those coins (visible in Whitehole) as keyframe points. This camera will only use 2 time keyframes. 

---

### Make sure your reference objects are in the <u>___MAIN GALAXY___</u>, not the zone!
![alt text](images/java_0pqVM1ZEZH.png)
`HoneyBeeKingdomGalaxy`✅

![alt text](images/java_zaM4kiYbIQ.png)
`ForestHomeZone`❌

---

Now, this might be confusing, so I'll try and go through this as step-by-step as possible.

First, let's set up the keyframes. It'll be easier if we set these up first, trust me.

Starting off, for a simple Point A to B camera, you'll want to make 2 camera timing points for each Position and Target entry. Under `Keyframe Data` you can enter the frame number in the `Time` slot.

If you're opening a CANM file from the base game, you'll see a lot of timing points. You'll probably want to delete most of the existing ones. Especially for a simple camera such as the one we're making here.

![alt text](images/LaunchCamPlus_0qqYjjrO6T.png) Before
![alt text](images/LaunchCamPlus_NL6GmtUWeI.png) After

<sub>(Tip, you can press CTRL + A to create a new timing point, and CTRL + DEL to delete the currently highlighted timing point.)</sub>

Next, look at the position of coin A.

![alt text](images/java_UXNHHY6Zdi.png)

Take note of these coordinates. Then, in LaunchCamPlus, take the X, Y, and Z positions from coin A, and put them in the corresponding `Position` sections first frames.



## Examples

### *Roll:* 0 to -180
![alt text](<images/rolling from 0 to positive 180.gif>)
### *Roll:* 0 to +180
![alt text](<images/rolling from 0 to -180.gif>)
### *Field of View:* 0 to 90
![alt text](<images/r FOV 0 to 90.gif>)

*Written by Syreyup*