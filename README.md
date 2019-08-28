# fzf-pass

This is a script heavily inspired by [rofi-pass](https://github.com/carnager/rofi-pass), but with FZF instead of Rofi. There's still a lot to do and this is just the first version. As it is now, it is only compatible with [Sway](https://github.com/swaywm/sway) (see TODO section)

### TODO
- Figure out a way to keep ydotool running after the popup terminal closes. Right now we can only support Sway because swaymsg is used to move the terminal out of the way
- Add detection for different fields, and show them only if they are there. Right now every field is hardcoded
- Add copy to clipboard option

### Installation
For Arch Linux users, there is an [AUR package](https://aur.archlinux.org/packages/fzf-pass). For all others, just download the script and point to it in your keybind.

### Usage

Add a keybind to your Sway config like so:
```bash
bindsym $mod+p exec $term --class fzf-pass -e sh -c fzf-pass

```

To make instances of fzf-pass float, here's how you can do it:
```bash
for_window [app_id="fzf-pass"] focus, floating enabled, border pixel 1

```

### Contributing
Any contributions are welcome! You can submit your PR's at [my Git server](https://git.reekynet.com/ReekyMarko/fzf-pass) (this is what I would prefer) or the mirrors at [GitLab](https://gitlab.com/ReekyMarko/fzf-pass) or [GitHub](https://github.com/ReekyMarko/fzf-pass)

You can also report bugs and submit feature requests at the issue trackers on the previously mentioned platforms.
