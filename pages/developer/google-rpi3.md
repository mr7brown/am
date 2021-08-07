---
title: Google - Raspberry Pi Set Up
layout: portfolio-developer
permalink: google-rpi3.html
folder: mydoc
---

## Overview

Prior to prototyping, it is recommended that you use the [Raspberryi Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
(Pi) to embed the Google Assistant and create custom actions that will work with
your device. This page provides a brief introduction to the Pi, the hardware
required to embed the Assistant, and how to install the Google Assistant SDK.

### Required hardware

Before configuring your Pi, you will need the following components:

* Micro-USB cable
* USB microphone (see [recommended](https://www.adafruit.com/product/3367))
* Speaker (see recommended [USB](https://www.adafruit.com/products/3369) or [3.5mm-jack](https://www.sparkfun.com/products/14023))
* Ethernet cable (if you are not using WiFi)
* MicroSD card reader
* 8 GB or larger microSD card (with [NOOBS](https://www.raspberrypi.org/downloads/noobs/) pre-installed)

If you plan to connect the Pi to an external monitor, then you may also need:

* HDMI cable
* HDMI-enabled display
* USB mouse
* USB keyboard

### Connect Raspberry Pi

1. Insert micro SD card into your Pi.
2. Plug in USB microphone and USB or 3.5 mm speaker.
3. Connect the keyboard and mouse using the USB ports (be sure not to cover your
USB microphone if using one).
4. Connect monitor using the HDMI port.
5. Connect the ethernet Cable (if you are not using [Wi-Fi](https://www.raspberrypi.org/documentation/configuration/wireless/desktop.md)
on your Pi).

{% include image.html file="rpi3_.jpg" alt="Example RPI3" %}
<br>
Once the Pi is connected, boot it up and follow the prompts and recommended
settings until the Pi's home screen displays.

### Configure and test the audio

Before installing the sample code, you need to configure the Pi to use your microphone and speaker.

1. Locate USB microphone in your Pi.
*  You will need to write down or copy the card number and device number.
```
$ arecord -1
```
2. Locate speaker (USB and 3.5 mm speakers have the same process).
* Write down or copy the card and device numbers.
```
$ aplay-1
```
3. From the home directory (`/home/pi`) create a file named `.asoundrc`.
4. Update the `.asoundrc` file with the correct slave definitions for microphone
and speaker.
* Use the configuration below, but replace `<card number>` and `<device number>`
with the card and device numbers that were copied in the previous steps. Complete this for
both `pcm.mic` and `pcm.speaker`.
```
pcm.!default {
  type asym
  capture.pcm "mic"
  playback.pcm "speaker"
}
pcm.mic {
  type plug
  slave {
    pcm "hw:<card number>,<device number>"
  }
}
pcm.speaker {
  type plug
  slave {
    pcm "hw:<card number>,<device number>"
  }
}
```
5. Play a test sound. If you hear the sound, press <b>Ctrl+C</b>.
```
$ speaker-test -t wav
```
* If you do not hear a sound, try adjusting the volume. (Press the up arrow key
to set the playback volume level to around 70.)
```
$ alsamixer
```
6. Record an audio clip.
```
$ arecord --format=S16_LE --duration=5 --rate=16000 --file-type=raw out.raw
```
7. Playback the recording.
```
$ aplay --format=S16_LE --rate=16000 out.raw
```

If the audio recording and playback is working, then the initial configuration
is complete. If not, check the microphone and speaker connections and try
again.
