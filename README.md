# Wheel Wizard U
 
Wheel Wizard U is a GPLv3 native Wii U homebrew foundation for managing a
legally installed Retro Rewind setup. It runs as a Cafe OS RPX, reads the SD
card, reports the installed Retro Rewind version and required files, accepts
Wii U GamePad input, and can hand off to either the vWii Menu or a user-supplied
vWii forwarder title.
 
The repository does not contain Mario Kart Wii, Nintendo code or assets,
Retro Rewind assets, or a forwarder. Use your own legally dumped PAL `RMCP01`
disc and obtain Retro Rewind from its official project.
 
## Current scope
 
This first native Wii U version provides:
 
- a Cafe OS frontend displayed on both the TV and GamePad;
- SD-card detection for the official `RetroRewind6` and launcher layout;
- strict parsing of the installed Retro Rewind version;
- optional launch of a configured vWii forwarder through `nn_cmpt`;
- a portable, tested core that can be reused by an updater; and
- an explicit manifest boundary for a future WiiCompiled Wii U runtime.
 
It does **not** claim that WiiCompiled currently runs on Wii U. Upstream
WiiCompiled targets desktop x64/ARM64 and relies on SDL and Dawn/WebGPU. A real
native port needs a Cafe OS runtime for GX2 graphics, AX audio, VPAD/KPAD input,
networking, storage, and OS services. See [the porting plan](docs/PORTING.md).
Until that runtime exists, the game itself runs through vWii; this manager is
the native Wii U component.
 
## SD-card layout
 
For Aroma, copy the built WUHB and example configuration to:
 
```text
sd:/wiiu/apps/wheelwizard-u/wheelwizard_u.wuhb
sd:/wiiu/apps/wheelwizard-u/config.ini
```
 
The RPX is also emitted for Homebrew Launcher setups that require it.
 
The scanner recognizes both the current Retro Rewind launcher layout and the
older Riivolution XML location:
 
```text
sd:/RetroRewind6/Code.pul
sd:/RetroRewind6/version.txt
sd:/RetroRewind6/xml/RetroRewind6.xml
sd:/apps/RetroRewind/boot.dol
