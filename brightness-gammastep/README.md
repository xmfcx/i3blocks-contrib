# brightness-gammastep

A lightweight multi-monitor brightness controller for **i3blocks** using `gammastep`.

* Adjusts brightness for **all connected displays**
* Works with any monitor supported by `gammastep`
* Uses a safe clamped range (0.1–1.0)
* Persistent brightness level stored in `~/.cache`
* Smooth scroll-based increments

## Ranges

| Value | Software (`gammastep -b`) | Hardware (`ddc-bright`) |
| --------- | ------------------------- | ----------------------- |
| 10 to 100 | 0.10 to 1.00              | 0                       |
| 100 to 200 | 1.00                     | 0 to 100                |

`ddc-bright` maps the hardware level per monitor. It runs in the background, one call at a time. A burst of scroll events collapses into the last value.

## Controls

| Action       | Result                                   |
| ------------ | ---------------------------------------- |
| Left click   | **100**: software max, hardware 0        |
| Middle click | **200**: everything max                  |
| Right click  | **10**: software min                     |
| Scroll up    | Increase by `STEP_SIZE`                  |
| Scroll down  | Decrease by `STEP_SIZE`                  |

## Setup / Installation

Make it executable:

```
chmod +x i3blocks-contrib/brightness-gammastep/brightness-gammastep
```

## Usage (i3blocks configuration)

Example block:

```
[brightness-gammastep]
label=☀
command=$SCRIPT_DIR/$BLOCK_NAME/$BLOCK_NAME
interval=1
STEP_SIZE=10
color=#e0e0e0
```

