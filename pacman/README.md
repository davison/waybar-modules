# pacman-upgrades

Shows the number of packages awaiting upgrade on the local system (has no output if there are none). 


## Example Config

You can use it as follows;

```jsonc
    "custom/pacman": {
        "format": "{}",
        "return-type": "json",
        "escape": true,
        "interval": 3600,
        "exec": "$HOME/projects/waybar-modules/pacman/pacman-upgrades",
        "on-click": "alacritty --hold -e 'yay -Syyu'" // optional
    }
```

In the example shown, hovering over the module will show a tooltip with the packages requiring the upgrade. Clicking on it should open a terminal (change if you don't use `alacritty`) to process the upgrades.

Set the following in your waybar directory's `style.conf` and adjust to taste

```css
#custom-pacman {
    color: #f55;
}
```

## Installation and Dependencies

Requires [`extra/pacman-contrib`](https://archlinux.org/packages/extra/x86_64/pacman-contrib/) - additional scripts for working with `pacman` on Arch.
