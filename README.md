# Dual Shifting Status Patch
This patch has been created as an improvement on the original [dualstatus patch](https://dwm.suckless.org/patches/dualstatus/) which allowed you to have two bars on screen at the same time, on the top and bottom

This patch allows you to change the placement of the two bars as you please, both bars can either be placed
- At the top and bottom as before
- At the top and you can switch between them with the `bartoggle` binding
- At the bottom and you can switch between them with the `bartoggle` binding

**Usage:**
The placement can be changed with one number, the macro `WHEREBARS` is used to determine the positioning of the bars
- 0 means - both on the bottom
- 1 means - both on the top
- 2 means - default bar on top and the second bar on the bottom
- 3 means - second bar on top and the default bar on the bottom
