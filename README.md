# source_food
An art installation that uses plants as switched to run gifs on raspberry pis

# HARDWARE
Running on Raspbian Jessie with PIXEL, Raspberry Pi B+
16GB SD card (6)
Adafruit 5pad touch sensor 
Wiring https://learn.adafruit.com/capacitive-touch-sensors-on-the-raspberry-pi/wiring
NB: Copper wire from 5pad to plant is flat copper tape 10cm long. *Longer wire makes it too sensitive.*


# SOFTWARE
Initial programming taken from https://learn.adafruit.com/capacitive-touch-sensors-on-the-raspberry-pi/programming-5-pad-momentary

NB: I followed this to set it up so that the 5pad.py script runs on boot 
https://raspberrypi.stackexchange.com/a/57560

QUOTE:

"For the past month or so I've been working on basically the exact same thing, so I've researched how to do this a lot and know how to do it with the latest version of Raspbian (PIXEL).

nodm is a minimal display manager that bypasses loading LXDE, and openbox (which is already installed on the Pi) provides a minimal session manager and works with the X server.

To set up this environment in Raspbian, install nodm with apt-get and edit the file /etc/default/nodm. You need to set the option NODM_ENABLED to true and NODM_USER to pi (or whatever your username is).

Then create a custom Xsession file in your home folder (/home/pi/.xsession) with the following contents (the while loop isn't necessary, it just automatically restarts the Python script if it crashes):

BEGINS

#!/usr/bin/env bash
exec openbox-session &
while true; do
  python3 /home/pi/Documents/script.py
done

ENDS"
