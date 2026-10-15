# RuneManager

A mod manager for DELTARUNE. It backs up your game before touching anything,
installs mods from a patch file or an archive, and puts everything back the
way it was with one button.

Windows only. Free.

## What it does

- **Backs up first.** Before any mod is applied, your clean game files and your
  save files are copied into `backups\`. Nothing is overwritten until that copy
  exists.
- **One-click restore.** `RESTORE VANILLA GAME` rebuilds the game from those
  copies. `RESTORE SAVE FILE` rolls your saves back to any earlier backup.
- **Mods never stack.** Turning a mod off rebuilds from vanilla rather than
  trying to undo a patch, so you can't end up with two mods half-applied on top
  of each other.
- **Version checking.** Deltamod/G3M packages carry checksums for the game files
  they expect. A patch built for a different version of DELTARUNE is refused
  instead of corrupting your install.
- **Conflict detection.** Two mods that want to change the same file are shown
  in red before you apply anything.

## Install

1. Download the latest release and unzip it anywhere.
2. Double-click `RuneManager.exe`.
3. On the GAME tab it should find your Steam copy on its own. If not, press
   BROWSE FOLDER and point it at your DELTARUNE folder.

### If Windows blocks it

Two different messages, two different fixes:

- **"Windows protected your PC"** with a *More info* link — click More info, then
  Run anyway. This is the normal warning for any program without a paid code
  signing certificate.
- **"blocked an app that may be unsafe"** — that's Smart App Control, which has
  no override. Use the Python version instead, which is the same program:
  install Python from python.org (tick *Add python.exe to PATH* on the first
  screen), then double-click `RuneManager.pyw`.

### For .xdelta mods

Most Deltarune patches are `.xdelta`, which needs a helper program:

1. Get the Windows x86_64 build from
   [xdelta-gpl releases](https://github.com/jmacd/xdelta-gpl/releases)
2. Rename the exe inside to `xdelta3.exe`
3. Drop it in the `tools\` folder

`.bps` patches work with no extra download.

## Mod formats

| Format | Notes |
| --- | --- |
| `.xdelta` | needs xdelta3.exe in `tools\` |
| `.bps` | built in |
| `data.win` | full replacement |
| loose files | copied into the game folder |
| `.zip` `.7z` `.rar` | archives of any of the above |
| Deltamod / G3M | `modding.xml` and `meta.toml`, including checksums |

It cannot run mods that need UndertaleModTool scripts (`.csx`) or ship their own
installer program. Those have to be done by hand.

## The tabs

| Tab | What it's for |
| --- | --- |
| GAME | find the game, back up, restore, launch |
| MODS | turn mods on and off, see conflicts, apply |
| DOWNLOAD | one-click installs, and a GitHub search for more |
| BROWSE | search GameBanana's Deltarune mods and install one directly |
| SAVES | edit a save file (find a value, name it, change it) |
| PRESETS | record save values and write them back later |
| SHARE | turn your mod list into a code to send someone |

## If something goes wrong

1. GAME → RESTORE VANILLA GAME
2. Steam → DELTARUNE → Properties → Installed Files → Verify
3. If the manager itself crashed, there's a `crash.log` next to the exe. Open an
   issue and paste it in.

## Built with AI assistance

The code was written with AI assistance (Claude), then tested and debugged
against a real DELTARUNE install. The full source is in this repo and in the
download, so you can read exactly what it does before running it. No AI
generated art, music or voices are used anywhere — the pixel font is drawn
glyph by glyph in code and the background is a gradient formula.

## Support

This is free and always will be. I don't have PayPal or Cash App, so if you want
to throw something my way, there's a dev product in my Roblox game. Go in, click
the Shop button in the bottom left, and there's one for 20 Robux. There's a 500
one too for anyone who really wants to, but just get the 20 one, I'm not greedy.

https://www.roblox.com/games/104485400718650/Voxel-Sandbox-Destruction

Totally optional. Bug reports help just as much.

## Notes

RuneManager is a fan tool. It contains no part of DELTARUNE and it doesn't host
anyone's mods — every download comes from that mod author's own release page.
DELTARUNE is by Toby Fox.
