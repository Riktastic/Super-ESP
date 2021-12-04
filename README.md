# Super-ESP
An Arduino sketch for ESP32's, to easily configure WiFi, NTP, DNS, MQTT, a webbased controlpanel and an API.

## What it is?
Super-ESP is a easy to use fullblown template for your own creations.
This template has been inspired by Tuya's ESP32 WiFi lightbulbs.
It allows us to:
 - Join a WiFi network (while making sure DNS works and an internet connection can be established),
 - Provide a lightweight webpage, with authentication and an API (making use of the SPIFSS filesystem for easily storing files. Just as you would on a normal webserver),
 - The webpage is templatable. By adding custom tags you can insert new informatie or open the .html-files to change the style of the webpage.
 - Sync the time with a NTP server,
 - Connect to a secure (as in SSL/TLS) MQTT broker,
 - Configure the device using the "configuration.json"-file on the SPIFFS filesystem,
 - Configure the device using MQTT and using the Web API,
 - Update the firmware usng MQTT and the Web API (can be done by providing a URL to a firmware file). Also known as OTA,
 - Has a 2D array to easily add GPIO-pins as new MQTT/website/API on/off-switches.
 - Modules such as: MQTT and the website/api can easily be removed from the compiled firmware.
 - It provides stability by checking for corrupt configurations and trying multiple times to connect to WiFi, NTP and MQTT.


## What is it not?
 A preconfigured script to automatically hookup your sensor/devices. You will have to program them manually. This is just a head start, in comparison to beginning from an empty sketch.
 

## Why is everything in 1 file?

This is everything you will need to customize the code. All of the used libraries have a great documentation.
It does not become a spaghetti code, atleast as long as everything has been correctly labeled, seperated and commented.
All of these design choices make it easy to implement your own functionality.
To be honest, this is not a philosophy. I recommend splitting code in different files and classed. Haven't exactly figured out a method that does not make it messy.


## To Do:

 1. The webserver library does not work with HTTPS. We should either wait for a fix or implement a different library. See: https://github.com/me-no-dev/AsyncTCP/pull/90
  - This one seems great. But to make this sketch ESP32 compatible and EPS8266 compatible we would have to implement both in the same script.

