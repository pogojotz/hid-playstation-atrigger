Patched hid-playstation driver
==============================

This driver exports the two RW sysfs attributes `left_atrigger` and
`right_atrigger`. Both can be written to a string of up to 11 numbers
(0-255), which are directly written to the left and right adaptive
trigger parameters in the output report. E.g.

```
# Pulse 20Hz
echo 38 255 255 255 255 255 255 0 0 20 > /sys/bus/hid/devices/0003:054C:0CE6.0002/left_atrigger

# Steam Controller like
echo 2 190 200 255 > /sys/bus/hid/devices/0003:054C:0CE6.0002/left_atrigger
```

See e.g. https://github.com/Mxater/DualSenseSupport/blob/master/DualSenseSupport/DeviceInfo.cs
for some of the known parameters meaning.
