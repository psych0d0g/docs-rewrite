---
ID: 32434
post_title: Picroft
author: Kathy Reid
post_excerpt: ""
layout: page
permalink: http://mycroft.ai/?page_id=32434
published: false
---
# Picroft

Picroft is an **Enclosure** for Mycroft, designed to the run on Raspberry Pi 3 or newer models. Mycroft provides the software for Picroft, in the form of a disk image, but you will need to burn this to an SD card.

Picroft is based on [Raspbian Jessie Lite](http://downloads.raspberrypi.org/raspbian_lite/images/).

**PICROFT will not work on earlier models of Raspberry Pi, because they do not have enough processing power.**

### Prerequisites

This section of documentation assumes the following:

* That you have the hardware prerequisites for running Picroft
* That you are comfortable connecting devices to WiFi networks
* That you are comfortable issuing basic Linux commands from a **terminal** or **shell prompt**

#### Hardware prerequisites

##### Required

* Raspberry Pi 3
* Micro SD card, 8GB or larger _highly_ recommended
* Power adapter with micro USB for your country. [The Raspberry Pi Foundation has some excellent recommendations](https://www.raspberrypi.org/documentation/hardware/raspberrypi/power/README.md).
* An analog Speaker that can be plugged into the 3.5mm audio jack on the RPi 3
* USB Microphone

##### Optional

* USB keyboard
* Monitor or TV connected via HDMI cable
* Ethernet cable (if not connecting via WiFi)

At the time of writing, a Picroft hardware kit is **not available** in the Mycroft Shop, but we are considering it. Please [see this Mycroft Forum discussion on which microphones and speakers are best used with Picroft](https://community.mycroft.ai/t/easiest-mic-speaker-option-for-raspberry-pi-3/1246).

#### Hardware recommendations

Below is information on specific hardware that has been tested with Picroft. If you have further recommendations, please raise an Issue or a Pull Request (PR) on this page.

##### Working Microphones

* **Blue Snoball/Snoball Ice** - Works very well
* **CM108 Based Mics** - The CM108 chip drives many low-priced microphones in various form-factors (if you run 'lsusb' you'll see them as _C-Media Electronics, Inc. CM108 Audio Controller_.  All work, but some are better than others for Picroft purposes.
   * eBerry Plug and Play Home Studio - decent experience, fair range
   * Kinobo Makio - functional, but only works at close range
* **[Jabra Speak410 USB Speakerphone](http://amzn.to/2kriCvh)** - Microphone and Speaker in the same device. Microphone range is good and speaker sound is loud and crisp.
* **[mVox USB Speakerphone](http://amzn.to/2jYCxR3)** - Microphone and Speaker in the same device. Microphone range is poor and speaker sound is bad compared to the Jabra Speak410.
* **[PS3 Eye Camera](http://amzn.to/2jFC6MP)** - Affordable and microphone range is good.

##### Incompatible Microphones
* _None at this point_

##### Working Speakers

* **Logitech Z50** - Mono speaker, wired, simple, can be found for cheap.

### Getting Started

#### Downloading the disk image

First, download the [Picroft disk image, available from the Picroft repo on GitHub](https://github.com/MycroftAI/enclosure-picroft).

#### Burn the disk image to the Micro SD card

Next, the disk image needs to be burnt to the Micro SD card.

The [Raspberry Pi official documentation provides an excellent tutorial](https://www.raspberrypi.org/documentation/installation/installing-images/) on this, using Etcher software. We recommend that you burn the Picroft image to the Micro SD card using Etcher.

![Etcher SD card image burning tool](../img/etcher-screenshot.png "Etcher SD card image burning tool")

#### Booting up Picroft

Once you've burned the Micro SD card, insert the Micro SD card into the Micro SD card slot on the Raspberry Pi. Plug in your microphone, speakers, and if you're using a monitor and/or keyboard, plug these in too.

Next, plug in the power and switch the power on.

####  Getting Picroft connected to the internet using a network cable

Plug the Picroft into your router using an ethernet cable plugged into the RJ45 port on the Raspberry Pi.

When Picroft boots, it will look for a network connection and will prompt you to set up a WiFi connection if a wired connection is not found.

#### Getting Mark 1 connected to the internet using Wifi

Using your computer or a mobile device, connect to the Wifi SSID `MYCROFT` using the password `123456787`. Once you are connected to this SSID, go to the web page [http://start.mycroft.ai](https://start.mycroft.ai). A list of available WiFi networks will be presented. Select the WiFi network that you wish to connect the Picroft to, and enter the WiFi password. Picroft will attempt to connect to the WiFi network.

_NOTE: Picroft cannot connect to WiFi networks that operate in the 5GHz band. You must select a WiFi network that operates in the 2.4GHz band._

@TODO I don't know what the limitations are around the WiFi networks that Mycroft can connect to - for instance, can Mycroft connect to WiFi networks that use certain types of authentication like WEP, or enterprise WPA2-PSK with things like Radius that are used in the enterprise? Don't know, flagging as @TODO

### Pairing the Picroft

Once the Picroft is connected to the internet, a **Registration Code** will be Spoken.

[View the home.mycroft.ai documentation to learn how to add your **Device** to home.mycroft.ai](/03.your-home.mycroft.ai-account/01.your-home.mycroft-account.md).

Once paired, you can then use [basic **skills**](../03.your-home.mycroft.ai-account/02.basic-commands.md).

#### Connecting to Picroft via SSH

* First, ensure that you've enabled SSH access.
@TODO is SSH on Picroft enabled by default?

* Ensure you know the IP address of your Mark 1 Device on your network. A handy way to do this is to install the IP Address **Skill**, and then Speak:

`hey mycroft, what's your IP address?`

`here are my available IP addresses: wlan IP address ... Those are all my available IP addresses`

* Open up your favorite terminal program, like PuTTy on Windows, or a new terminal on Linux
* `ssh pi@IPADDRESS`
* The default password is `mycroft`, so enter this when prompted.
* If you have successfully logged in via SSH you will see a command prompt like the one below:

```
$ ssh pi@192.168.0.13
pi@192.168.0.13's password:

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Oct 18 13:02:44 2017
pi@mark_1:~ $
```

You are now connected to Picroft via SSH.

#### How to reimage a Picroft Device

@TODO Not sure how to do this - I'm assuming it's as easy as burning a new image to the SD card?

#### Keeping your Picroft updated

The easiest way to keep your Picroft updated is to burn a new disk image to your Micro SD card, and re-pair your Picroft Device.

@TODO Not sure if this is the best way to keep Picroft updated - is there an easier way?

### Common issues on Picroft Devices

@TODO link to Troubleshooting

### Hardware Hacking your Picroft Device

@TODO need to touch base with @penrods on what should go in here