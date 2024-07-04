<h1>Just a couple of adjustments that I usually make whenever I use GNOME as my default DE</h1>

<h3>Changing the timeout of the "App is not responding popup".</h3>

The default time is set to 5 seconds. In order to change it to a higher value or to remove it, follow these steps.

1. Open the terminal and paste these values:

    To 60 seconds:
        
        gsettings set org.gnome.mutter check-alive-timeout 60000

    To completely disable it:

        gsettings set org.gnome.mutter check-alive-timeout 0

2. Enjoy

<h3>Changing the volume increment step".</h3>

If I am not mistaken, the default value of the step is 6% and I don't like, it is too much when I am switching volume using my keyboard. Follow these steps to change the value:

1. Open the terminal and set the desired value (I like to set at 3%)

        gsettings set org.gnome.desktop.sound volume-step 3

2. Enjoy