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
5. Connect your phone to the Raspbeery Pi through USB and *“Allow USB debugging”* on your phone in the popup.

When you checked that everything works you should change the SSH password and update sitespeed.io and NodeJS.

### Log into the device
Use the user `pi` and password `tearsofaclown` to log into the device using SSH.

### Changing SSH login password
Login to the device and change the password to your new password using `passwd`.

### Run tests
You can run the test on the phone:
```
sitespeed.io https://www.sitespeed.io --android
```

If you want to use the internet connection of your Rapsberry Pi and throttle it (in this example as a 4g network) you can run like this:

```
sitespeed.io https://www.sitespeed.io --android --connectivity.engine throttle -c 4g --gnirehtet
```

### Connect using vnc

On your Mac, open “Screen Sharing” and then use *raspberrypi.local* as the hostname and the password *browsertime*. You will then be able to see the Raspberry PI screen on your Mac. 

On you Raspberry Pi you can start *scrcpy* (open a terminal and write  *scrcpy*) and you will see the phone screen on the Raspberry Pi desktop.

### Update your device
There's probably a newer version of sitespeed.io so install that:

```
npm install -g sitespeed.io
```

There's also probably a newer version of NodeJS. Use [latest LTS](https://nodejs.org/en/) and at the moment when I write that it is NodeJS 16.
```
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install nodejs
```

