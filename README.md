Thank you for your interest in the project. This is meant as a starter template in your journey to Wezterm for you to configure for your own needs.

If you came from my YouTube video, there has been a few updates to enhance your experience:

* Customizable Prefix Indicator Symbol
* New rounded style tabs for the tab bar
* Optional border around Wezterm

# Quickstart

Put `wezterm.lua` in `$HOME/.config/lua`, or alternatively, see wezterm [documentation](https://wezterm.org/config/files.html#configuration-files)
# Configuration:
## Leader Active Prefix
The main feature of interest in this configuration is the indicator that the leader key is active. When the leader key is active, you will see the wave icon on the bottom left `utf-8: 1f30a`: 🌊

You may also change this to any utf8 character you want:

```lua
-- leader active indicator prefix
local leader_prefix = utf8.char(0x1f30a) -- ocean wave
```

## Basics
Leader is set to `ALT q`, and the timeout is 2s, you can change it easily in `config.leader`:

```lua
config.leader = { key = "q", mods = "ALT", timeout_milliseconds = 2000 }
```

## Border
The border is enabled by default - you may disable it by commenting the entire section out, or modify it to your liking:

```lua
config.window_frame = {
    border_left_width = "0.4cell",
    border_right_width = "0.4cell",
    border_bottom_height = "0.15cell",
    border_top_height = "0.15cell",
    border_left_color = colors.border,
    border_right_color = colors.border,
    border_bottom_color = colors.border,
    border_top_color = colors.border,
}
```

## Rounded vs Square Tab Bar
Two new styles to choose from by setting the tab_style to `rounded` or `square`:

```lua
local tab_style = "rounded"
```
or
```lua
local tab_style = "square"
```
Try both to see which one you like!

## Colors
Colorscheme is set to `Catppuccin Macchiato`, you may change it to any of the [available colorschemes](https://wezterm.org/colorschemes/index.html) for wezterm.

```lua
config.color_scheme = "Catppuccin Macchiato"
```
If you want the tab bar to match your theme, please note that you must also change the color palette in the `colors` section:

```lua
-- color scheme colors for easy acccess
local scheme_colors = {
    catppuccin = {
        macchiato = {
            rosewater = "f4dbd6",
            flamingo = "f0c6c6",
            pink = "f5bde6",
            mauve = "c6a0f6",
            red = "ed8796",
            maroon = "ee99a0",
            peach = "#f5a97f",
            yellow = "#eed49f",
            green = "#a6da95",
            teal = "#8bd5ca",
            sky = "#91d7e3",
            sapphire = "#7dc4e4",
            blue = "#8aadf4",
            lavender = "#b7bdf8",
            text = "#cad3f5",
            crust = "#181926",
        }
    }
}

local colors = {
    border = scheme_colors.catppuccin.macchiato.lavender,
    tab_bar_active_tab_fg = scheme_colors.catppuccin.macchiato.mauve,
    tab_bar_active_tab_bg = scheme_colors.catppuccin.macchiato.crust,
    tab_bar_text = scheme_colors.catppuccin.macchiato.crust,
    arrow_foreground_leader = scheme_colors.catppuccin.macchiato.lavender,
    arrow_background_leader = scheme_colors.catppuccin.macchiato.crust,
}
```

## Font
Font: `Maple Mono`, size `14`:

```lua
config.font =
    wezterm.font_with_fallback { "Maple Mono NF", "JetBrains Mono NL" }
config.font_size = 14
```
