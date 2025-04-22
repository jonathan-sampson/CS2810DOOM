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
