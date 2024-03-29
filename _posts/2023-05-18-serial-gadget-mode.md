---
layout: post
title: 'Enabling Serial Gadget Mode on a Raspberry PI'
---

* Write a fresh Raspberry PI OS Lite to your micro-sd.
* Boot the Pi with the fresh card to allow the OS to resize the partitions.
* Remove the card from the Pi and mount the boot and root partions.
* Add ***dtoverlay=dwc2*** to the end of BOOT/config.txt
* Add ***modules-load=dwc2,g_serial*** after ___rootwait__ in BOOT/cmdline.txt
* In a terminal, cd to ROOT/lib/systemd/system/getty.target.wants
* Run ___sudo ln -s ../getty@.service ./getty@ttyGS0.service___
* umonunt the partiions and boot from the card.
* In a terminal, run ___picocom /dev/ttyACM0___

### References
- https://www.tal.org/tutorials/setup-raspberry-pi-headless-use-usb-serial-console
