# Install

## Requirements

After completing the following steps, you should have completed the follwing requirements:

- The `eww` binary is in your path, accessible as `eww`.
- The `rancid` script is executable and in your path, accessible as `rancid`.

## Install `eww`

See the official `eww` [documentation](https://elkowar.github.io/eww/) for instructions on how to install `eww`.

## Install `rancid`

1. Clone the `rancid` [GitHub repository](https://github.com/Snxwman/rancid) into your `$HOME/.config` directory.

```bash
git clone https://github.com/Snxwman/rancid "$HOME/.config"
```

2. Make the `rancid` scrip executable.

```bash
sudo chmod +x rancid
```

3. Create a symbolic link to the rancid script, in a directory in your path (e.g. `/opt`, `/usr/local/bin`, or `~/.local/bin`).

```bash
sudo ln -s $(pwd)/.install/rancid /opt
```

4. [Configure](config.md) `rancid`.

5. Start `rancid` as you would start a stand alone install of `eww`.

```bash
rancid daemon
rancid open <window>
```
