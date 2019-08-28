# fzf-pass

This is a script heavily inspired by [rofi-pass](https://github.com/carnager/rofi-pass), but with FZF instead of Rofi. There's still a lot to do and this is just the first version. As it is now, it is only compatible with [Sway](https://github.com/swaywm/sway) (see TODO section)

## TODO
- Figure out a way to keep ydotool running after the popup terminal closes.
- Add detection for different fields, and show them only if they are there. Right now every field is hardcoded
- Add copy to clipboard option

## Usage
**AUR package coming soon**

Add a keybind to your Sway config like so:
```
bindsym $mod+p exec $term --class fzf-pass -e sh -c path/to/fzf-pass.sh

```

To make instances of fzf-pass float, here's how you can do it:
```
for_window [app_id="fzf-pass"] focus, floating enabled, border pixel 1

```
