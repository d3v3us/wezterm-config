Thank you for your interest in the project. This is meant as a starter template in your journey to Wezterm for you to configure for your own needs.

# Quickstart

Put `wezterm.lua` in `$HOME/.config/lua`, or alternatively, see wezterm [documentation](https://wezterm.org/config/files.html#configuration-files)

### Configuration:

Leader is set to `ALT q`, and the timeout is 2s, you can change it easily in `config.leader`:

```lua
config.leader = { key = "q", mods = "ALT", timeout_milliseconds = 2000 }
```

Colorscheme is set to `Catppuccin Macchiato`, you may change it to any of the [available colorschemes](https://wezterm.org/colorschemes/index.html) for wezterm.

```lua
config.color_scheme = "Catppuccin Macchiato"
```

Please note that you would also need to change the color of the arrow foreground to match the new color scheme:


```lua
wezterm.on("update-right-status", function(window, _)
    ...
    local ARROW_FOREGROUND = { Foreground = { Color = "#c6a0f6" } } -- color:mauve
        ...
        if window:active_tab():tab_id() ~= 0 then
            ARROW_FOREGROUND = { Foreground = { Color = "#1e2030" } } -- color:mantle
        ...
        window:set_left_status(wezterm.format {
            { Background = { Color = "#b7bdf8" } }, -- color:lavendar
```

Font: `JetBrains Mono NL`, size `16`:

```lua
config.font =
    wezterm.font("JetBrains Mono NL")
config.font_size = 16
```

# Leader Active

The main feature of interest in this configuration is the indicator that the leader key is active. When the leader key is active, you will see the wave icon on the bottom left `utf-8: 1f30a`: 🌊

You may also change this to any utf8 character you want:

```lua
prefix = " " .. utf8.char(0x1f30a) -- ocean wave utf8 character
```

