# Introduction
### Total Time Spent:


## Phases

### Project setup

- spent ~2 hours to learn about and fix build errors:
- build error 1
- error 2
- build error 3
- spent ~1 hour getting necessary dependencies set up:
- Xephyr display software
- installed library 1
- installed library 2
- Learned that sound doesn't really work anymore from dating, and that re-implementing sound into this code would be a few orders of magnitude of difficulty above my understanding
- Beginning modification
- Read code. I read a __lot__ of code.

### First Modification: Hyperspeed! (player)
#### The first modification I implemented was higher player speed.

This modification was quite simple, and only took changing a few lines of code. I didn't even need any knowledge of C or understanding of the game engine to implement this. I simply parameterized the `P_MovePlayer` function and declared a global variable `modded_speed` at the beginning of the `p_user.c` file. (It was initially 2048, which I doubled to 4096)

### Second Modification: *SUPER* Hyperspeed! (enemy)
#### The second modification I implemented was far higher enemy speed.

This modification was also quite simple, and is very comical to observe. The enemy speed was simply stored in an array `mobjinfo` in `info.c`. Then, due to good documentation, I was able to easily locate the speed value of the Former Humans, Former Human Sergeants, and Imps, and manually multiply each speed value by `5`. This results in very fast enemies that are quite hard to gun down in the game.

### Third modification: Hyperspeed! (weapons)
#### The third modification I implemented was higher fire rate for three weapons.

This modification was a bit more challenging to implement, but was again as simple as modifying constant values in the `info.c` file; in the `states` array (line 135), each weapon's fire rate is defined with a tic delay before that weapon can be fired. I found the data for the in-game punch attack, the pistol, and the shotgun, which are the first three attainable weapons, and reduced each to the minimum value of `1`. The result is Mike Tyson-level punching speed and inhuman firing speed of the other two weapons. (Unfortunately, the very fast player speed makes this impractical.)

### Fourth modification: Aurora Borealis (background)
#### The fourth modification I implemented was a beautiful background to gaze upon.

I decided that my monster-slaying wasn't quite aesthetic enough. I've always loved the Northern Lights, so I decided to make the sky have the texture. Unfortunately, this was *far* more complicated than expected. I had to learn about IWADs (internal WADs that contain all the game data), PWADs (path WADs which contain patches or "overwrites" to the game data), how to format an image appropriately so that the Doom engine will read it properly, and a multitude of other niche bits of Doom knowledge. (To view this effect, gaze out the window of the first window. It's on the right of the very first level as soon as you walk out of the elevator.)

### Fifth modification: Custom DOOM Text
#### The fifth modification I implemented was custom background text on the title screen.

For this modification, I used my newly-acquired WAD editing skills to spice up the background text! On the title screen, instead of "DOOM", it now reads "CS2810 Final." For this modification, I once again had to dig through the WADs, locate the texture that represents the "DOOM" text on the title screen, make my *own* texture that reads "CS2810", convert it into a Doom Palette compatible texture using SLADE, and then replace the original texture. I'm pretty happy with how it turned out, but the Doom palette (8-bit color) is pretty restrictive.

### Crosshair implementation

#### The x modification I implemented was a crosshair, which is notably missing from Classic *Doom*. 


- Read rendering code
- The crosshair is a 2D overlay that will be drawn on top of the game, centered on screen




# Summary of Code Changes:
## The result of running `diff` in the terminal for different files is recorded below







make sure to run the environment variable DISPLAY=:2 in another shell instance
        
sudo Xephyr :2 -ac -screen 640x480x8 in terminal 1
./linux/linuxxdoom -2 in terminal 2

sudo Xephyr :2 -ac -screen 640x480x8
./linux/linuxxdoom -2
