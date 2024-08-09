# squeezebox

Given a Logitech Media Server (squeezebox) and a player name, displays the current song/station and artist information in the bar. Clicking the info in the bar toggles play/pause.

Playing...
![](./screenshot1.png)

Paused...
![](./screenshot2.png)


## Example Config

You can use it as follows, adjust any paths based on your install locations;

```jsonc
"custom/squeezebox": {
    "interval": 5,
    "format": "🎜 {} {percentage}%",
    "return-type": "json",
    "exec": "$HOME/waybar-modules/.venv/bin/python $HOME/waybar-modules/squeezebox/squeezebox 10.1.2.3 Office",
    "on-click": "$HOME/waybar-modules/.venv/bin/python $HOME/waybar-modules/squeezebox/squeezebox 10.1.2.3 Office toggle"
}
```

The args to the script are as follows;

 * `lms_ip` the IP address of your squeezebox server
 * `player_name` the name of the player you want to track, as shown in your LMS player list
 * `toggle` \[optional\] if present will cause the player to toggle between play and pause state, so useful mostly as a click target

These are the classes (adjust as you like) that should be in your `style.css` for waybar;

```css
#custom-squeezebox.pause, #custom-squeezebox.stop {
    color: #ccc;
}

#custom-squeezebox.play {
    color: #2f2;
}
```

## Installation and Dependencies

Requires `python3`, `pysqueezebox` and `aiohttp` to work..

```bash
sudo apt install python3
cd ~/waybar-modules
python -m venv .venv
source .venv/bin/activate
pip3 install pysqueezebox aiohttp
```
(or similar based on your distro)
