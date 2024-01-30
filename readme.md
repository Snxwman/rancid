# rancid

## Installation

### Requirements

- The `eww` binary **must** be in your `PATH`, accessible as `eww`.
- The `rancid` script **must** be in your `PATH` accessible as `rancid`.

### Quick start

1. Clone this repository into `$HOME/.config/`
2. Make the `rancid` script executable.
3. Copy the `rancid` script into `/opt/`
4. Configure rancid.
5. Start rancid.
6. Open configured windows.

```bash
git clone https://github.com/Snxwman/rancid.git "$HOME/.config/"
```
```bash
sudo chmod +x rancid
```
```bash
sudo ln -s "$HOME/.config/rancid/rancid" /opt
```
```bash
rancid daemon
```
```bash
rancid open bar
```

## Structure
```
rancid
  ├── custom
  │   ├── override.scss        User configured style overrides
  │   ├── theme.scss           User theme selection
  │   └── user.yuck            User theme selection 
  ├── scripts
  ├── styles
  │   ├── util.scss            Utility variables definitions
  │   └── *.scss               Rancid widget themes
  ├── themes
  │   └── *.scss               Theme color variable definitions
  ├── widgets
  │   ├── util.yuck            Widgets used as components of other widgets
  │   └── *.yuck               Widgets accessible to user config
  ├── eww.scss                 Base gtk element themeing
  └── eww.yuck                 Rancid pre-configured windows
```

## Special yuck variables

```yuck
(defvar theme "tokyonight")
```

The built-in theme used for styling widgets. If you do not want to use a built in theme, set to an empty string. 

