# pavolume

You can run this script to subscribe to pulseaudio (pactl subscribe) and detect changes.
Everytime you lower, raise or mute, the script will poll PA for the information and echo it out.

I build this to have a small volume text added to my tint2 bar but you can use it for whatever you like, I guess.

# Installation
**If you're not using Swedish you'll have to edit the grep on line 7, as well as the "ja" on line 19**

Put the script anywhere in your path, run it, fiddle with the volume, hopefully it works.


# tint2 integration

I have shamelessly copied the bottom of the config belonging to @brontosaurusrex
https://github.com/brontosaurusrex/postbang/blob/master/.config/tint2/tint2rc

The only thing changed is the execp_command set to pavolume and the click commands modified for pactl instead of the alsamixer.
```
#------------------------------------
# E = EXECP
execp = new
execp_centered = 1
execp_has_icon = 0
execp_command = pavolume
#execp_interval = 0
# behaves well, looks good:
execp_continuous = 1
execp_font = cuprum 8
execp_font_color = #ffffff 100
execp_padding = 0 0 0
# disable this tooltip to get update info
execp_tooltip = volume
#execp_background_id = 0
execp_padding = 2 0 2
execp_mclick_command = pactl set-sink-mute @DEFAULT_SINK@ toggle
execp_rclick_command = pactl set-sink-volume @DEFAULT_SINK@ +5000
execp_lclick_command = pactl set-sink-volume @DEFAULT_SINK@ -5000
execp_uwheel_command = pactl set-sink-volume @DEFAULT_SINK@ +1000
execp_dwheel_command = pactl set-sink-volume @DEFAULT_SINK@ -1000
```
