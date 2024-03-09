# State

This page documents the expected structure of core state variables. 
All state in eww is either a string or json.

# Table of Contents

- [System](#system)
    - [Audio](#audio), [Datetime](#datetime), [Networking](#networking), [Desktop](#desktop)
- [Apps](#apps)
    - [Weather](#weather)
- [Configuration](#configuration)
    - [provider](#provider), [icons](#icons)

# System

## Audio

```yuck
(defvar audio "{}")
```

```json
{
    "default": {},
    "audio": {
        "devices": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "sinks": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "sources": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "streams": [
            {
                "id": "",
                "nick": "",
            }
        ]
    },
    "video": {
        "devices": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "sinks": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "sources": [
            {
                "id": "",
                "nick": "",
            }
        ],
        "streams": [
            {
                "id": "",
                "nick": "",
            }
        ]
    },
}
```

## Datetime

### Datetime

```yuck
(defpoll datetime :initial "{}" :interval "1s" "./scripts/datetime")
```

```json
{
    "date": {
        "year": "2024",
        "month": {
            "name": "February",
            "short": "Feb",
            "number": "02"
        },
        "day": {
            "name": "Friday",
            "short": "Fri",
            "number": "23"
        }
    },
    "time": {
        "hour": {
            "f24": "20",
            "f12": "08",
            "ampm": "PM"
        },
        "minute": "13",
        "second": "21"
    }
}
```

### Uptime

```yuck
(defpoll uptime :initial "{}" :interval "1s" "./scripts/uptime")
```

```json
{
    "seconds": {
        "total": "33186",
        "until-minute": "6"
    },
    "minutes": {
        "total": "553",
        "until-hour": "13"
    },
    "hours": {
        "total": "9",
        "until-day": "9"
    },
    "days": {
        "total": "0",
        "until-week": "0",
        "until-month": "0",
        "until-year": "0"
    },
    "weeks": {
        "total": "0",
        "until-month": "0",
        "until-year": "0"
    },
    "months": {
        "total": "0",
        "until-year": "0"
    },
    "years": 0
}
```

Fields named `until-XYZ` represent the number of units until `XYZ`.
All fields are an integer greater than or equal to zero.

## Networking

### Ethernet

```json
```

### Wi-Fi
```json
{
    "ssid": "my-wifi",
    "gateway": "10.0.0.1",
    "dns": "1.1.1.1 , 8.8.8.8",
    "ipv4": "10.0.0.82",
    "strength": "79"
}
```

### Bluetooth

```json
{
    "controller": {
        "name": "BlueZ 5.72",
        "powered": "yes",
        "discoverable": "no",
        "pairable": "yes",
        "discovering": "no",
        "blocks": {
            "soft": "false",
            "hard": "false"
        }
    },
    "devices": [
        {
            "name": "My AirPods Pro",
            "mac": "",
            "icon": "audio-headphones",
            "paired": "yes",
            "connected": "no",
            "battery": ""
        },
        {
            "name": "Adv360 Pro",
            "mac": "",
            "icon": "input-keyboard",
            "paired": "yes",
            "connected": "yes",
            "battery": ""
        },
        {
            "name": "WH-1000XM4",
            "mac": "",
            "icon": "audio-headset",
            "paired": "yes",
            "connected": "yes",
            "battery": "60"
        },
        {
            "name": "MX Master 3S",
            "mac": "",
            "icon": "input-mouse",
            "paired": "yes",
            "connected": "yes",
            "battery": "35"
        }
    ]
}
```

### VPN

```json
```

## Desktop 

### Wallpaper

```yuck
(defvar wallpaper [])
```

```json
[
    {
        "image": "~/media/photos/wallpaper/32:9/1329159.jpg",
        "thumb": "~/media/photos/wallpaper/32:9/1329159.jpg.thumb"
    },
    {
        "image": "~/media/photos/wallpaper/32:9/2043645.png",
        "thumb": "~/media/photos/wallpaper/32:9/2043645.jpg.thumb"
    },
    {
        "image": "~/media/photos/wallpaper/32:9/2043659.jpg",
        "thumb": "~/media/photos/wallpaper/32:9/2043659.jpg.thumb"
    }
]
```

For performance reasons, loading a full scale, full quality image is not recommended.
Additionally, `pngs` images take noticably longer to load per image than `jpg` images.

To combat this, it is recommended to transform all the full images into thumbnails.
An example conversion command can be found [here](https://github.com/Snxwman/scripts/blob/main/mkthumb).

### Window Manager

```yuck
(defvar wm-state [])
```

```json
[
    {
        "name": "main",
        "icon": "",
        "active": false,
        "open_window": true,
        "screen": null,
        "screen_icon": null,
        "layout": "columns",
        "layout_icon": "",
        "layouts": [
            {
                "name": "columns",
                "icon": ""
            },
            {
                "name": "floating",
                "icon": ""
            }
        ]
    }
]
```

```json
{
    "workspaces": [
        {
            "name": "",
            "icon": "",
            "active": true,
            "screen": "",
            "layout": "",
            "open_windows": true,
            "windows": [
                {
                    "name": "",
                    "icon": "",
                    "focused": true,
                    "visible": true,
                }
            ],
            "layouts": [
                {
                    "name": "",
                    "icon": "",
                    "active": true
                }
            ],
        }
    ],
    "screens": [
        {
            "name": "",
            "icon": "",
            "workspaces": []
        }, ...
    ],
}
```

The top level array should have one object per workspace.

## System

### Packages

```json
[
    "pacman": {
        "updates": [],
        "total_pkgs": 63,
        "main_repos": 61,
        "other_repos": 2,
        "main_pkg": 17,
        "dep_pkgs": 44
    },
    "asdf": {
        "new_latest": [
            "python",
            "rust"
        ]
    }
]
```

# Apps

## Music

```yuck
```

```json
{
    "spotify": {
        "status": "",
        "title": "",
        "artist": "",
        "album-name": "",
        "album-art": "",
        "position": "",
        "length": "",
    }
}
```

## Weather

```yuck
(defpoll :initial "{}" :interval "5m" "")
```

```json
```

# Configuration

## providers

```yuck
(defvar providers '{ ... }')
```

This variable does not get updated automatically.

```json
{
    "packages": [
        "pacman"
    ],
    "term": "kitty",
    "wm": "qtile"
}
```

## icons

```yuck
(defvar icons '{ ... }')
```

This variable does not get updated automatically.

```json
{
    "bluetooth": "󰂯",
    "calendar": "󰃮",
    "clock": "",
    "wifi": {
        "off": "󰤭",
        "zero": "󰤯",
        "low": "󰤟",
        "med": "󰤢",
        "high": "󰤥",
        "full": "󰤨",
        "no-net": "󰤫"
    },
    "device": {
        "headphones": "󰋋",
        "earphones": "󱡏",
        "mouse": "󰍽",
        "keyboard": "󰌌"
    },
    "battery": {
        "unknown": "󰂑",
        "charging": "󰂄",
        "zero": "",
        "low": "",
        "med": "",
        "high": "",
        "full": ""
    },
    "audio": {
        "input": "󰍬",
        "input-mute": "󰍭",
        "output": "󰕾",
        "output-mute": "󰖁",
        "zero": "󰕿",
        "low": "󰖀",
        "med": "󰖀",
        "high": "󰕾"
    },
    "wm": {
        "normal": "",
        "active": "",
        "window-open": ""
    },
    "hardware": {
        "cpu": "",
        "gpu": "󰢮",
        "ram": "󰑭",
        "disk": "󰋊",
        "net": ""
    }
}
```

*Values shown above are the default values*

