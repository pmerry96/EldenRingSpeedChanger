# EldenRingSpeedChanger
This is a lua script for cheat engine to dynamically change the speed of Elden ring (or any other game) dynamically with the help of cheat engine

I ***HIGHLY** Recommend running Elden Ring offline with the EAC Disabled. Steps to do that are here:
https://www.windowscentral.com/how-disable-anti-cheat-elden-ring

Please note this script is to be run in Cheat Engine 7.5, I havent tested it on previous versions

STEPS TO USE

Step 1: Launch Cheat Engine 7.5
Step 2: Attach Cheat Engine to the Elden Ring process
Step 3: Load the file "SpeedChanger.CT"
Step 4: Press ctrl+alt+L
Step 5: Click Execute Script

--- 
Script Controls

HOTKEYS:

F3 - Start the game speed changer
F4 - Stop the game speed changer
F1 - Use the "random" speed changer type (Jumpy, random changes in speed)
F2 - Use the "Sine" speed changer type (continuous, smooth change in speed)

Tunable parameters (Edited in the SpeedChanger.CT lua script):

baseSpeed: Works in 2 different ways, depending on using sin or random for speed changer type
	If using sine:
		This is the "middle" speed of the speed changer. IE, if you want to oscillate between 0.5x speed and 2x speed, the baseSpeed is 1.25
	If using rand:
		This is the maximum speed that you can achieve, and you will randomly select a value between 0 and the base speed. IE, if you want
		to randomly select any speed between 0x and 500x, set this to 5. 

maxspeed: A hard cap on the maximum speed any speed changer can set the game speed to.

minspeed: A hard floor on the minimum speed any speed changer can set the game speed to. Setting this to 0 or below will crash your game. 

sinfreq: Only applicable for the Sine speed changer. Increase this value for the speed to change more every time the speed updates. Decrease this value to decrease the change in speed every time the speed updates
sinamp: Only applicable for the Sine speed changer. The amount of deviation from the baseSpeed that can be achieved. (IE: speed range is baseSpeed plus or minus sinamp)

TimeInterval: This is the frequency with which the script will actually attempt to change the speed. Default set to 300 milliseconds. If the script is causing lag, increase this value. 
