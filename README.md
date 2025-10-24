# Overview
This is a minimal build of DWM and i have done some changes in both `dwm.c` but i've basically overhauled `config.def.h` and i have tried to keep it as minimal of a system as possible

But in this readme i will only be going through my `config.def.h`, what i've changed in my layouts, keybindings, workspace/tag settings etc. and i'll mention the patches i've applied to `dwm.c`
## Patches
- [alwayscenter](https://dwm.suckless.org/patches/alwayscenter/)
	- centers all floating dialogs to the center of the screen
- [blanktags](https://dwm.suckless.org/patches/blanktags/)
	- replaces the numbers on the workspace/tag area on the top left into empty boxes
- chargecolor - my own custom patch that I built with the help of **[@elbachir-one](https://github.com/elbachir-one/)**
	- built for laptops
	- when the charger is unplugged, it turns all borders and the status bar red, when plugged in the colors go back to being blue
	- the colors can of course be changed in the `config.h` file
- dualshiftingstatus - an improvement on the **dualstatus** patch that i created which lets you move two bars into four seperate configurations
	- both on top, overlapping
	- both on bottom, overlapping
	- main bar on top and extra bar on bottom
	- extra bar on bottom and main bar on bottom
- commandbase - this isnt a patch for dwm but for dmemu that i created, it allows the user to define commands, instead of executables, to be placed in dmenu search where the user can search for them
	- it has a file that you can configure with any commands that you use often but dont want to type them out
	- any number of commands can just be placed in here and on refreshal of dmenu, the commands will be accessible as search items
## Static Settings
### Bar setup
I have disabled the bar, it is completely unnecessary to the point where i dont even notice it on my screen, legitimately if i want to look at the time i will look at my phone, i just get that tunnel-visioned while working - so i just hid the bar a while ago and haven't turned it on since
### Font settings
` static const char *fonts[]			   = { "Hasklig:bold:size=14" }; `
- I have changed the font and the font size for the status bar
- I tried haskell for a few days, it was pretty nice but extremely slow development so i left and i found the font while i was over there
### Color/theme settings
- I have removed all the pre-defined colors with a new color system that takes in three color sets and then colors the statusbar and the borders accordingly
- In this system three presets are provided, the original color theme, a blue theme and a red theme
	- More themes can be added for both the current_theme and the alternate_theme, you just need to define them seperately or redefine the colors in the current themes
- These themes are put to use by the chargecolor patch to change theme according to the state of my battery, if it is plugged in then the theme is blue and if unplugged the theme will be red
- This is part of my custom chargecolor patch
### Workspace settings
- I have reduced my total workspaces to be 6, i dont really need more than that
- I dont really have workspaces anymore, i replaced the numbers with the blanktags patch
- Also as i mentioned before i hid the bar so i dont even look at those things anymore, i know where everything is so i just use dwm without anything
- My setup has basically become all screen and nothing else
### Workspace setup

| 1<br>Work | 2<br>Research/<br>Questions | 3<br>Entertainment  | 4<br>File<br>Management/<br>Creation |   5<br>Device Connectivity    | 6<br>Audio Management |
| :-------: | :-------------------------: | :-----------------: | :----------------------------------: | :---------------------------: | :-------------------: |
|   Xterm   |     Ungoogled-chromium      | Discord<br>web-app  |               Nautilus               |            Blueman            |      Easyeffects      |
|           |      Gemini<br>web-app      | Youtube<br>web-app  |               Obsidian               |    KDEConnect<br>settings     |      Pavucontrol      |
|           |                             | Whatsapp<br>web-app |                                      |       KDEConnect<br>sms       |                       |
|           |                             | Discord<br>web-app  |                                      |       KDEConnect<br>app       |                       |
|           |                             |                     |                                      | CUPS settings page<br>web-app |                       |
### Layout
I've made the main layout to be monocle and the tiling layout to be secondary, i want all my focus on the thing im working on and not on something thats open on the side or in the background, so everything is fullscreen - always
### Key definitions
In dwm there is already `Mod1Mask` and `ShiftMask` but i didnt really like that naming scheme, so i changed all of them and added some of my own
```
#define ALT		Mod1Mask
#define CTRL	ControlMask
#define SHIFT	ShiftMask
#define SUPER	Mod4Mask
```
## Keybindings
**Custom**

| Key           | Function   |
| ------------- | ---------- |
| alt-s         | flameshot  |
| super-shift-b | u-chromium |
| super-shift-l | slock      |



**Navigation**



| Key         | Function                      |
| ----------- | ----------------------------- |
| alt-space   | rofi                          |
| super-b     | hide/show bar                 |
| alt-tab     | recent workspace              |
| alt-a       | move to next window in stack  |
| alt-shift-a | move to prev window in stack  |
| super-j     | move window to master view    |
| super-k     | move window to master view    |
| super-h     | resize master window to left  |
| super-l     | resize master window to right |
| super-enter | switch window in master area  |


**View Manipulation**



| Key               | Function                             |
| ----------------- | ------------------------------------ |
| ctrl-shift-=      | close window                         |
| super-ctrl-j      | monocle layout                       |
| super-ctrl-k      | tiling layout                        |
| super-ctrl-l      | no layout \| floating windows        |
| super-space       | previous layout                      |
| super-shift-space | toggle floating on current window    |
| super-0           | bring all workspaces into view       |
| super-shift-0     | pin current window on all workspaces |
| super-shift-q     | logout                               |
As said before i changed the tag keys from 9 to 6 and i didnt really change any of the mouse bindings since i dont use the mouse that much
