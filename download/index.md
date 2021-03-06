---
layout: download
banner: true
title: Download & Setup OctoPrint
description: Learn how to setup OctoPrint using the preinstalled OctoPi image for Raspberry Pi, or how to install from source on Windows, Linux and Mac.
---

# OctoPi

[Guy Sheffer](https://github.com/guysoft) maintains ["OctoPi"](https://octopi.octoprint.org),
a [Raspbian based](http://www.raspbian.org/) SD card image for the Raspberry Pi
that already includes OctoPrint plus everything you need to run it:

* OctoPrint plus its dependencies
* [MJPG-Streamer](https://github.com/jacksonliam/mjpg-streamer)
  for live viewing of prints and timelapse video creation, compatible with various
  USB webcams and the Raspberry Pi camera
* [CuraEngine 15.04](https://github.com/Ultimaker/CuraEngine) for slicing directly
  on your Raspberry Pi

You can download the latest version via the following button:

<div class="text-center">
    <a class="btn btn-large btn-block" href="https://octopi.octoprint.org/latest" data-event-category="download" data-event-action="latest"><i class="icon-download-alt icon-large"></i>&nbsp;&nbsp;Download&nbsp;OctoPi&nbsp;0.14</a>
    <small>MD5Sum of the .zip: <code>52c855c9bcc88fd3bf81bbe8e58a2e4c</code></small><br>
    <small>
        <strong>Recommended Model Raspberry Pi 3</strong><br>
        Compatible with Raspberry Pi A, B, A+, B+, B2<br>
        <strong>Not Recommended Models Raspberry Zero and Zero W</strong><br>
        * The Pi Zero and Zero W are Not recommended if you plan to use a webcam for a live view <br>
        the wifi interface currently <a href="https://github.com/guysoft/OctoPi/issues/318#issuecomment-284762963" target="_blank">causes significant CPU load</a>
         on bandwidth utilization, negatively affecting running print jobs.
</div>

or simply buy one of the available

<div class="text-center">
    <a class="btn btn-large btn-block" href="/support-octoprint/#kits" data-event-category="download" data-event-action="kits">All-in-one OctoPrint Kits</a>
</div>

##  Getting Started with OctoPi

Please follow these steps after downloading

1. Unzip the image and install the contained ``.img`` file to an SD card
   [like any other Raspberry Pi image](https://www.raspberrypi.org/documentation/installation/installing-images/README.md).
2. Configure your WiFi connection by editing ``octopi-network.txt`` on the root of the
   flashed card when using it like a thumb drive.
3. Boot the Pi from the card.
4. Log into your Pi via SSH (it is located at ``octopi.local``
   [if your computer supports bonjour](https://learn.adafruit.com/bonjour-zeroconf-networking-for-windows-and-linux/overview)
   or the IP address assigned by your router), default username is "pi",
   default password is "raspberry". **Change the password** using the ``passwd``
   command. You do not need to expand the filesystem, current versions of OctoPi do this automatically.
5. Access OctoPrint through ``http://octopi.local`` or ``http://<your pi's ip address>``. https is available too,
   with a self-signed certificate.

Please also refer to [OctoPi's README](https://github.com/guysoft/OctoPi), especially the ["How to use it" section](https://github.com/guysoft/OctoPi#how-to-use-it).

[Thomas Sanladerer](https://www.youtube.com/channel/UCb8Rde3uRL1ohROUVg46h1A) created a great video guide on how to get OctoPi 0.12 up an running.

{% include youtube.html vid="MwsxO3ksxm4" %}

----

#  Installing from source

The generic setup instructions boil down to

1. Installing [Python 2.7](https://www.python.org/) including [pip](https://pip.pypa.io/en/latest/installing.html) and [virtualenv](https://virtualenv.pypa.io/en/stable/installation/).
2. Obtaining the source through either of:
   1. cloning the [source repository](https://github.com/foosel/OctoPrint.git): `git clone https://github.com/foosel/OctoPrint.git`
   2. downloading an [archive of the current stable version](https://github.com/foosel/OctoPrint/archive/master.zip) from Github and unpacking it
3. Creating a (user owned) virtual environment in the source folder: `virtualenv venv`
4. Installing OctoPrint *into that virtual environment*: `./venv/bin/python setup.py install`
5. OctoPrint may then be started through `./venv/bin/octoprint` or with an absolute path `/path/to/OctoPrint/venv/bin/octoprint`

More specific setup instructions for the most common runtime environments can be found below.

##  Linux

For installing OctoPrint from source, please take a look at [the setup instructions for Raspbian on the wiki](https://github.com/foosel/OctoPrint/wiki/Setup-on-a-Raspberry-Pi-running-Raspbian).
They should be pretty much identical on other Linux distributions.

##  Windows

For installing OctoPrint on a Windows system, please take a look at [the setup instructions for Windows on the wiki](https://github.com/foosel/OctoPrint/wiki/Setup-on-Windows).

## Mac

For installing OctoPrint on a Mac, please take a look at [the setup instructions for MacOS on the wiki](https://github.com/foosel/OctoPrint/wiki/Setup-on-Mac).

----

