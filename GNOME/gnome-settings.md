# Just a couple of adjustments that I usually make whenever I use GNOME as my default DE

Changing the timeout of the "App is not responding popup".

The default time is set to 5 seconds. In order to change it to a higher value or to remove it, follow these steps.

1. Open the terminal and paste these values:

To 60 seconds:
```plaintext 
gsettings set org.gnome.mutter check-alive-timeout 60000
```
To completely disable it:
```plaintext
gsettings set org.gnome.mutter check-alive-timeout 0
```
2. Done

# Changing the volume increment step

If I am not mistaken, the default value of the step is 6% and I don't like, it is too much when I am switching volume using my keyboard. Follow these steps to change the value:

1. Open the terminal and set the desired value (I like to set at 2%)
```plaintext
gsettings set org.gnome.settings-daemon.plugins.media-keys volume-step 2
```
2. Check if the changes were applied by running this command:
```plaintext
gsettings get org.gnome.settings-daemon.plugins.media-keys volume-step
```
3. Done
