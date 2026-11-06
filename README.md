# The Hourglass

A vintage hourglass of walnut and gold for the MEGA65, and a timer: set it from 5 minutes to an
hour, in steps of 5, turn it, and the upper bulb runs empty in exactly the time you chose.

It is a demonstration of our physics engine too. Each of its 6,336 grains of sand is simulated on
its own, frame by frame, as it falls, slides and comes to rest: the stream through the neck, the
crater that opens in the upper bulb and the cone that rises in the lower one are the grains' own
doing, not an animation. And it is a demonstration of sound: what you hear comes from the same physics, a soft
burst from the SIDs for every grain that lands on the pile and the hiss of the stream while it
runs, then a bell of three strikes when the last grain lands.

Version 1.0, 6 November 2026.

![The hourglass at rest, the time to choose: five minutes](docs/the-hourglass-select.png)

A 47-second video, with sound: [docs/the-hourglass.mp4](docs/the-hourglass.mp4). A five-minute
run: the turn and its first twelve seconds as they happen, the sand's sound switched off and on
again with S, the middle twelve times faster and silent, then the last grains and the bell.

## Run

Needs a MEGA65. Made for PAL (50 Hz); the engine keeps time in NTSC (60 Hz) too, but that has run
only in an emulator.

1. Download `HOURGLASS.D81` from the [latest release](https://github.com/psincosoft/hourglass/releases/latest)
   and copy it to the SD card.
2. `MOUNT "HOURGLASS.D81"`
3. `LOAD"*",8,1`, then `RUN`

The disk's SHA-256: `5b4f91c8c67b564b1b037d4a4218af28f39bc1439cf82b259f9dfedb5baba675`.

The opening card, then the hourglass, its sand at rest in the lower bulb.

## Keys

| Key | What it does |
|---|---|
| CRSR left and right, or the stick | the time, 5 minutes to 1 hour in steps of 5, while the glass rests |
| RETURN, SPACE, or FIRE | turn the glass. While it runs too: what has fallen runs back, as in a real hourglass |
| S | the sand's sound, off and on |
| B | the bell, off and on (a bell that sounds stops) |
| Q or RUN/STOP | the end |

S and B show the new setting to the left of the glass for two seconds, then it fades. Both start
on. Both joystick ports work.

## What is in it

- **A timer.** The clock beside the glass counts down the time left. The neck lets the sand
  through at the rate that empties the upper bulb in the time chosen, from 5 minutes to an hour.
- **The physics.** Every grain is one pixel, simulated frame by frame by our own engine in machine
  code on the MEGA65's 40 MHz processor: it falls, slides down the slopes and settles, and the
  stream falls with gravity from the neck to the pile. The longer the time, the thinner the stream.
- **The sound.** Made by the SIDs from the physics, as it happens: a short burst of noise for each
  grain that lands, the hiss of the stream, softer when the stream is thinner. When the last grain
  lands, a bell on two more SIDs. No sample is used.
- **The picture.** The hourglass is rendered with Blender from a scene built in code, and shown on
  the 80 x 50 text screen in full-colour characters: 640 x 400 pixels in 256 colours.

## Pictures

![Half way: two and a half minutes left](docs/the-hourglass-running.png)

![S pressed: the sand's sound off](docs/the-hourglass-sand-off.png)

![The sand, closer: the crater over the neck, the stream, the cone](docs/the-hourglass-sand.png)

The pictures and the video are made on a PC from a model of the program that its engine matches
byte for byte, every frame; the sound is the same writes to the SIDs, played through an emulated
6581. They are not photographs of the machine.

## Tested on

A MEGA65 (R6A) in PAL, core 890-sdcard-native build #63 (commit 1c737937), ROM 920422.

## Credits

The Hourglass 1.0, 2026, by Dawid Blachowski, with Claude, Anthropic's AI.
psinco. A Software Atelier from Luxembourg.

- Written with Claude, Anthropic's AI, which wrote the code, built the scene and shaped the sound
  under Dawid Blachowski's direction.
- The hourglass rendered with Blender.
- The clock's digits and the settings' letters: the Lora typeface (Cyreal), SIL Open Font License
  1.1.
- Made with Python, NumPy, SciPy, OpenCV, Pillow, py65 and d64; the video with FFmpeg and reSIDfp.

## Terms

The Hourglass is free. You may download it, run it, show it, film it, and share the disk image
unchanged and free of charge. See [LICENSE](LICENSE).
