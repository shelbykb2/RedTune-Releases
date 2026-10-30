# RedTune

A free AMD Radeon GPU tuner for **Windows and Linux**. You can undervolt, overclock, set power limits and draw fan curves, and it's built to set and forget.

**[Download the latest release](https://github.com/shelbykb2/RedTune-Releases/releases/latest)**

- **Startup profile**: your daily tune goes on when you sign in.
- **Per-game profiles**: when a game launches, RedTune switches to that game's tune, and switches back when it closes.
- **Crash-safe**: if the driver crashes and wipes your tuning, RedTune keeps your profile but **never re-applies it on its own**. It tells you what happened, and you re-apply with one click, or back the undervolt off first.
- **Simple and Advanced modes**: three sliders (voltage offset, max clock, power limit) or every setting the driver exposes, including VRAM, memory timing, zero RPM and a draggable fan curve.

It works on RDNA cards (RX 5000 series and newer) through AMD's own driver interface on Windows (ADLX) and the `amdgpu` kernel driver on Linux. RedTune stays inside the limits the driver allows.

## Install

### Windows 10 / 11
1. Install the current AMD Software (Adrenalin) driver.
2. Download `RedTune-<version>-win-x64.zip`, unzip it anywhere and run `RedTune.exe`. No admin rights needed.
3. Optional: in **Settings**, turn on *Start RedTune when I sign in*.

If RedTune says the driver reports no manual tuning, open AMD Software → Performance → Tuning, pick **Manual** once and accept AMD's warning, then restart RedTune.

### Linux (x64)
```sh
tar xzf RedTune-<version>-linux-x64.tar.gz
cd linux-x64
sudo sh install.sh
```
Clock, voltage and fan tuning need GPU overdrive enabled in the kernel: add `amdgpu.ppfeaturemask=0xfff7ffff` to your kernel command line and reboot. Power limit and monitoring work without it, and RedTune tells you when it's off. Linux support is new; please report anything that doesn't work.

## Safety
Undervolting and overclocking can crash your PC. A crash costs you nothing but a restart, and RedTune is built so a bad tune can't keep crashing you: after a crash it stays on stock until you choose. **Hold Shift while RedTune starts** to skip applying anything for that launch.

## Feedback
Found a bug or have an idea? [Open an issue](https://github.com/shelbykb2/RedTune-Releases/issues).

## License
RedTune is free to use but closed source: it includes AMD's ADLX SDK, whose license allows shipping binaries only. See [EULA.txt](EULA.txt). Please share the link to this page rather than the files.

RedTune is not made by or affiliated with AMD. AMD and Radeon are trademarks of Advanced Micro Devices, Inc.
