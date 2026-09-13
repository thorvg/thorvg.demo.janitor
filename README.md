[![License](https://img.shields.io/badge/licence-MIT-green.svg?style=flat)](LICENSE)
[![Wikipedia](https://img.shields.io/badge/Wikipedia-000000?style=flat&logo=wikipedia&logoColor=white)](https://en.wikipedia.org/wiki/Thor_Vector_Graphics)
[![Discord](https://img.shields.io/badge/Community-5865f2?style=flat&logo=discord&logoColor=white)](https://discord.gg/n25xj6J6HM)
[![OpenCollective](https://img.shields.io/badge/OpenCollective-84B5FC?style=flat&logo=opencollective&logoColor=white)](https://opencollective.com/thorvg)

# Thor Janitor

<p align="center">
  <img width="600" height="auto" src="https://github.com/thorvg/thorvg.janitor/blob/main/title.png">
</p>

**“Clean the Galaxy, One Sweep at a Time!"**

By 2080, Earth's orbit has become a cosmic graveyard, a massive junkyard of space debris threatening the survival of humanity's spacefaring future. This is where you come in: the brave (if slightly underpaid) space janitor. Your enemies aren't fearsome alien warriors—they're just mountains of cosmic trash!<br />
<br />
You pilot a Thor Cleaning Ship, sweeping the orbit clean by blasting away these junk invaders. The more you clean, the safer and shinier Earth becomes. With your trusty ship, you'll blast through debris, protect humanity's future, and prove that even trash duty can make you a hero.<br />

<p align="center">
  <img width="800" height="auto" src="https://github.com/user-attachments/assets/8a4bd16a-bb72-4b41-b007-eadc2220d1eb"/>
</p>

<p align="center">
  <strong><a href="https://youtu.be/jdnnzmtHy9k">Watch the full video!</a></strong>
</p>

## Build & Run
Install Meson, Ninja, pkg-config, and a C++17 compiler, then install [ThorVG](https://github.com/thorvg/thorvg) and [ThorVG Toolkit](https://github.com/thorvg/thorvg.toolkit). The recommended ThorVG build option is
```
-Dloaders="svg,ttf,jpg"
```
Ensure `thorvg-toolkit` and `thorvg-1` are discoverable by pkg-config. Build and run from the repository root so relative asset paths resolve correctly:
```
$ meson setup build
$ ninja -C build
$ ./build/thorvg-janitor
```

Select the rendering backend with `-e <engine>`. The default is `sw` (CPU software rendering):
```sh
$ ./build/thorvg-janitor -e sw  # CPU (Software)
$ ./build/thorvg-janitor -e gl  # OpenGL
$ ./build/thorvg-janitor -e wg  # WebGPU
```
GPU backends require the corresponding support in your ThorVG and ThorVG Toolkit builds.

## Key Instruction

* **Arrow Key**: Movement
* **A** : Shoot
* **Esc** : Exit

## Combo System

You earn cleaning points for every piece of space junk you clear away.
Sweep away the same type of trash consecutively to trigger combo bonuses, multiplying your score for an even shinier cleanup!

## Features

- Designed as a demo app to showcase the performance of the ThorVG engine.
- Each enemy is composed of 86 particles, with up to ~300 enemies appearing on screen simultaneously.
- Includes a full-size background image (subtle halo glow effect, not distracting) and 4 layers of 100 star objects.
- At peak load, around 25,000 paint objects are rendered together.
- The player’s ship, missiles, and GUI texts feature real-time DropShadow effects, while zone outlines include real-time BlurEffects.
- Runs fully stable at 120+ FPS with the Software Renderer on 2K resolution.

## Authors

* **[Hermet Park](https://github.com/hermet)**
