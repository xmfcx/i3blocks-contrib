# brightness-xrandr

A lightweight multi-monitor brightness controller for **i3blocks** using `xrandr`.

* Adjusts brightness for **all connected displays**
* Works with any monitor supported by `xrandr`
* Uses a safe clamped range (0.1–1.0)
* Persistent brightness level stored in `~/.cache`
* Smooth scroll-based increments

## Controls

| Action      | Result                             |
| ----------- | ---------------------------------- |
| Left click  | Set brightness to **100%**         |
| Right click | Set brightness to **10%**          |
| Scroll up   | Increase brightness by `STEP_SIZE` |
| Scroll down | Decrease brightness by `STEP_SIZE` |


## Setup / Installation

Make it executable:

```
chmod +x i3blocks-contrib/brightness-xrandr/brightness-xrandr
```

## Usage (i3blocks configuration)

Example block:

```
[brightness-xrandr]
label=☀
command=$SCRIPT_DIR/$BLOCK_NAME/$BLOCK_NAME
interval=1
STEP_SIZE=10
color=#e0e0e0
```

