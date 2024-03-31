ZTM's Flexible HUD release 8
March 31, 2024
----------------------------

ZTM's Flexible HUD mod for ioquake3 (Quake 3 and Team Arena expansion).

For updates visit:

  * https://clover.moe/flexible-hud-for-ioq3

## Install

Download the zip and put the Flexible HUD pk3 files in your baseq3 and
missionpack folders.

If “vm” directory exists in ioquake3's baseq3 and missionpack folders
rename it to “vm-ioq3”, otherwise it will override the mod files in
Flexible HUD pk3.

This mod is based on the ioquake3 mod code. The default changes are that
the HUD will be aspect correct and the Quake 3 start server menu will
display 8 maps instead of 4. You can configure the HUD with cvars listed
below.

Flexible HUD mod is only compatible with Quake III Arena (baseq3) or
Team Arena (missionpack). It does not support other mods. For the
Flexible HUD mod to be used on multiplayer servers, the server needs to
allow client-side add-ons (set sv_pure cvar to 0) or install the
Flexible HUD pk3 files.

Most servers don't allow client-side add-ons (sv_pure 1) or run a mod.
This means Flexible HUD will not work on most public servers.

If you're playing single player, want instagib and/or unlagged modes,
or want to host a server for using this mod you would likely have a
better experience using Spearmint Quake 3.

  * https://clover.moe/spearmint


## New Cvars

* cg_stretch [0 – 1] stretch 4:3 HUD to fit screen (default: 0)

* cg_fovAspectAdjust [0 – 1] automatically convert 4:3 cg_fov values to current aspect (default: 0)
* cg_fovGunAdjust [0 – 1] controls gun offset based on FOV. 0 uses Q3A code, 1 uses new code (works with FOV < 90 and fixed FOV dmflags) (default: 0)

The following cvars all default to 1. Only cg_drawWeaponBar is usable in Team Arena.

* cg_statusScale [0.0 – 1.0] set scale of status bar (ammo, health, head, armor, CTF flag).
* cg_drawStatusHead [0 – 2] 0 disables drawing head, 1 acts like Q3A, 2 drawing health item instead (supports 3D and 2D icons).
* cg_drawPickups [0.0 – 1.0] set scale of item pickup message (0 to disable).
* cg_drawWeaponBar [0.0 – 1.0] set scale of weapon select popup (0 to disable).
* cg_drawScores [0 – 1] toggle drawing scores in bottom right corner (no scaling support).

### Recommended Settings

cg_stretch 0; cg_fovAspectAdjust 1; cg_fovGunAdjust 1; cg_fov 90;

To apply these settings, open the in-game Quake console using shift+escape
and paste the above command using ctrl+v and then press enter. Then use
shift+escape to close the console.

To use very high quality graphics settings run the following command:

exec ztm-ioq3-veryhighquality.cfg; vid_restart


## Source Code

The source code is available on GitHub licensed as GPLv2+ in the
zturtleman/flexible-hud-for-ioq3 repository.

To build it from a terminal use the following:

    git clone https://github.com/zturtleman/flexible-hud-for-ioq3.git
    cd flexible-hud-for-ioq3
    git checkout flexible_hud-r8
    make BUILD_SERVER=0 BUILD_CLIENT=0


## Other Notes

The pk3s contain cgame QVM for HUD changes. They also contains qagame and
ui QVMs. This allows me to distribute improvements to them (committed to
ioquake3) and fix local server player pain sounds due to ioq3's qagame <-> cgame
communication not being compatible with official Quake 3 QVMs.

cg_fovAspectAdjust is based on a formula posted by LordHavoc and
implemented in QtZ by Razor.

Widescreen support is based on Spearmint Quake 3. However, Spearmint
Quake 3 does not have cg_stretch 1, cg_drawStatusHead, cg_drawWeaponBar,
or HUD scaling options.


## Credits

Quake 3 - id Software
ioquake3 - ioquake3 contributors
4:3 FOV value to widescreen formula - LordHavoc
cg_fovAspectAdjust implementation - Razor
ZTM's Flexible HUD - Zack Middleton

