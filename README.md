# i3wm
configuration files for i3wm

## multi monitor setup:

For working with multiple monitors I've used a few lines of bash code so far.. however for more than one multi monitor setup a script might me more convenient.. 
So far I've been using e.g.:
```
exec_always(xrandr | grep  'VGA-0 connected' &> /dev/null) && (xrandr | grep '1920x1200\|1920x1080' &> /dev/null)  && xrandr --output VGA-0 --auto --primary --above LVDS
exec_always(xrandr | grep  'VGA-0 disconnected primary' &> /dev/null) && xrandr --output VGA-0 --off
exec_always(xrandr | grep  'HDMI-0 connected' &> /dev/null) && (xrandr | grep '1920x1080' &> /dev/null)  && xrandr --output HDMI-0 --mode 1920x1080 --primary --output LVDS --off
exec_always (xrandr | grep  'HDMI-0 disconnected primary' &> /dev/null) && xrandr --output HDMI-0 --off --output LVDS --mode 1366x768 --primary
```
