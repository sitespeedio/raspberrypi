# Raspberry Pi setup for Android phones

Use your Raspberry Pi4 to run tests on you Android phones. The images comes with the following pre installed:
* adb
* NodeJS, sitespeed.io and dependencies to record a video
* Chromedriver and Geckodriver
* Gnirenhet so you can reverse the traffic from your phone back to your Raspberry Pi and throttle your connection
* scrcpy and vnc so you can watch the desktop on you Raspberry Pi from your computer


## Install using the pre-made image
1. Download the pre-made image from [releases](https://github.com/sitespeedio/raspberrypi/releases).
2. Burn the image on a SD card using [Raspberry Pi Imager](https://www.raspberrypi.com/software/).
3. Insert the SD card into the Raspberry Pi 4.
4. Connect your Raspberry Pi with your router through a Ethernet cable and turn on your Raspberry Pi.
5. Connect your phone to the Raspbeery Pi through USB.

When you checked that everything works you the SSH password!

### Log into the device
Use the user `pi` and password `tearsofaclown` to log into the device using SSH.

### Changing SSH login password
Login to the device and change the password to your new password using `passwd`.

### Run tests

```sitespeed.io https://www.sitespeed.io --android```

```sitespeed.io https://www.sitespeed.io --android --connectivity.engine throttle -c 4g --gnirehtet```

### Connect using vnc

