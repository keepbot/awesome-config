# Awesome config

Thanks to **[Wei "pw" Peng](https://github.com/pw4ever)** who enspired me a lot! Look at his [awesome-wm-configh](https://github.com/pw4ever/awesome-wm-config).
Maybe in future I'll make all-in-one-ultimate-awesome-config. You can use GutHub issues for feature requests and any other offers. 

### Installation
I'd recommend use ArchLinux with this config, because of arch menu generation, but it isn't necessary.
Any dependencies you can find in rc.lua and change for something yours.

```
# Dependencies:
sudo pacman -S sacura terminator vim firefox spacefm gnome-commander doublecmd \
               pcmanfm tmux gnome-control-center gnome-alsamixer alsa-utils    \
               pm-utils gmrun scrot xorg-setxkbmap lxtask

git clone https://github.com/keepbot/awesome-config.git ~/.config/awesome

touch ~/.config/awesome/autostart.lua

# For arch users
~/.config/awesome/archmenu.gen
# For others
touch ~/.config/awesome/archmenu.lua

Modkey4+Control+r to restart awesome
```

### Autostart

You need to create file *autostart.lua* and add simple startup records like this:
```lua
-- run_once(prg,arg_string,pname,screen)
-- prg         - program name
-- arg_string  - startup arguments
-- pname       - process name
-- screen      - monitor location (tags [screen][x])

run_once("skype")
run_once("dropbox")
run_once("nm-applet")
run_once("empathy")
run_once("thunderbird")
run_once("firefox")
run_once("doublecmd")
run_once("pac")
```

### Rules

In **rc.lua** some rules are defined. You need to redifine them for your need or remove.

**Rules**
```lua
awful.rules.rules = {
    -- All clients will match this rule.
    { rule = { },
      properties = { border_width = beautiful.border_width,
                     border_color = beautiful.border_normal,
                     focus = awful.client.focus.filter,
                     raise = true,
                     keys = clientkeys,
                     buttons = clientbuttons } },
    { rule = { class = "Vlc" },
      properties = { floating = true } },
    { rule = { class = "Gimp" },
      properties = { tag = tags[1][5], floating = true } },
    { rule = { class = "Firefox" },
    properties = { tag = tags[1][2] } },
    { rule = { class = "Double" },
    properties = { tag = tags[1][3] } },
    { rule = { class = "Thunderbird" },
    properties = { tag = tags[1][4] } },
    { rule = { class = "Skype" },
    properties = { tag = tags[1][4] } },
    { rule = { class = "Empathy" },
    properties = { tag = tags[1][4] } },
    { rule = { class = "Pac" },
    properties = { tag = tags[1][6] } },
    { rule = { class = "Sublime" },
    properties = { tag = tags[1][7] } },
}
```

### Themes

To change theme you need to change theme name and main colour in *theme.lua*


I created following themes:
* Blue   - 'blue'
* Gray   - 'gray'
* Green  - 'green'
* Red    - 'red'
* Yellow - 'yellow'
* Zen    - 'zen'

*Screenshot:*
![BlueTheme](/screenshot/blue.png)

### Keyboard

To configure keyboard layout you neet to make apropriate changes in *kb.lua*. 
Defaut layout: *US* and *RU*. 
And key combination: Control+LeftShift (Which can be defined in *rc.lua*)

### License

> Copyright (c) 2016 Dmitry Ivanov
>
> Licensed under the Apache License, Version 2.0 (the "License");
> you may not use this file except in compliance with the License.
> You may obtain a copy of the License at
> 
>     http://www.apache.org/licenses/LICENSE-2.0
> 
> Unless required by applicable law or agreed to in writing, software
> distributed under the License is distributed on an "AS IS" BASIS,
> WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
> See the License for the specific language governing permissions and
> limitations under the License.
