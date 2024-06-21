# EldenRingSpeedChanger
This is a lua script for cheat engine to dynamically change the speed of Elden ring (or any other game) dynamically with the help of cheat engine

I **HIGHLY** Recommend running Elden Ring offline with the EAC Disabled. Steps to do that are here:
https://www.windowscentral.com/how-disable-anti-cheat-elden-ring

Please note this script is to be run in Cheat Engine 7.5, I havent tested it on previous versions

Theoretically, you can use this script for any non-online game provided you attach cheat engine to the game process

STEPS TO USE

Step 0: Clone this repository

Step 1: Launch Cheat Engine 7.5

Step 2: Attach Cheat Engine to the Elden Ring process

Step 3: Load the file "SpeedChanger.CT"

Step 4: Press ctrl+alt+L

Step 5: Click Execute Script


--- 
**Script Controls**

HOTKEYS:

F1 - Start the game speed changer

F2 - Stop the game speed changer

F3 - Set the game speed back to 100% 

F6 - Use the "random" speed changer type (Jumpy, random changes in speed)

F7 - Use the "Sine" speed changer type (continuous, smooth change in speed)

F8 - use the Sawtooth speed changer (linear increase from a min to a max or vice versa, then go to the opposite extreme)

F9 - Use the Linear wave speed changer (like a sine wave, but is a triangle wave)

F10 - Change if the sawtooth speed changer goes from min to max, or from max to min (default is from min to max)

---

**Tunable parameters**

(Edited in the SpeedChanger.CT lua script):

baseSpeed: Works in 2 different ways, depending on using sin or random for speed changer type

baseSpeed - If using sine: This is the "middle" speed of the speed changer. IE, if you want to oscillate between 0.5x speed and 2x speed, the baseSpeed is 1.25

baseSpeed - If using rand: This is the maximum speed that you can achieve, and you will randomly select a value between 0 and the base speed. IE, if you want to randomly select any speed between 0x and 500x, set this to 5. 

maxspeed: A hard cap on the maximum speed any speed changer can set the game speed to.

minspeed: A hard floor on the minimum speed any speed changer can set the game speed to. Setting this to 0 or below will crash your game. 

sinfreq: Only applicable for the Sine speed changer. Increase this value for the speed to change more every time the speed updates. Decrease this value to decrease the change in speed every time the speed updates

sinamp: Only applicable for the Sine speed changer. The amount of deviation from the baseSpeed that can be achieved. (IE: speed range is baseSpeed plus or minus sinamp)

TimeInterval: This is the frequency with which the script will actually attempt to change the speed. Default set to 300 milliseconds. If the script is causing lag, increase this value. 


The below parameters apply to a sawtooth or triangle/linear wave only

SawToothMax: the maximum speed a sawtooth speed changer can achieve (Cannot be greater than maxspeed)

SawToothMin: The minimum speed a sawtooth speed changer can achieve (cannot be les than minspeed)

SawToothPeriodMs: The amount of time it takes to go from one extreme to the other in milliseconds. For the sawtooth wave, this is the period Note, if using a linear wave - this 1/2 the period. This value cannot be less than TimeInterval

sawToothSign: This determines if the sawtooth wave is continuously increasing before reverting to min speed (default) or continuously decreasing before reverting to max speed. Do not edit, instead use the F10 hotkey

