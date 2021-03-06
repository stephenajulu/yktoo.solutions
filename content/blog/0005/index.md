---
title: "Sound Switcher Indicator 2.2.0"
date: "2019-01-13T21:49:20+02:00"
description: >-
    Sound Switcher Indicator version 2.2.0 has been released, featuring support for virtual devices and the all-new
    _Preferences_ dialog.
tags:
    - Linux
    - software
    - Sound Switcher Indicator
    - Ubuntu
categories:
    - software
author: "Dmitry Kann"
image: "/images/logos/sound-switcher-indicator-800.png"
---

It's time to fulfil [my promise](https://yktoo.com/en/blog/post/342), so please meet Sound Switcher Indicator version **2.2.0**.

## What's new {#whats-new}

There are the following two major differences with the previous release:

* Support for virtual devices ([#48](https://github.com/yktoo/indicator-sound-switcher/issues/48)) has been added: network *sources* and *sinks* from other PulseAudio servers are now also displayed in the indicator menu and can be switched to.
* A *Preferences* dialog has finally arrived. These days you can easily adjust the looks of the menu using a GUI (which was previously only possible by editing `$HOME/.config/indicator-sound-switcher.json`). A corresponding menu item has been planted:

{{< imgfig "menu.png" "Sound Switcher Indicator's menu." >}}

## Preferences dialog {#prefs-dialog}

The dialog features two tabs:

* The **General** tab allows to hide all inputs and/or outputs at once:
{{< imgfig "prefs-general.png" "Sound Switcher Indicator: General preferences." >}}
* The **Devices** tab configures device and port display:
{{< imgfig "prefs-devices.png" "Sound Switcher Indicator: Device preferences." >}}
* The **Refresh** button at top right reloads all devices and their ports so you don't need to reopen the dialog after device removal or addition.

All settings are applied on-the-fly after a short delay.

Other changes:

* A minor (yet breaking) change to the configuration file format. From now on the port configuration can only be an object (previously it was possible to use a string or `false`). This means you might need to update your config, which is a breeze with the new dialog.
* A long-outstanding bug with misplaced device items ([#55](https://github.com/yktoo/indicator-sound-switcher/issues/55)) has been fixed. Actually, the real issue is with GTK+ but I managed to work around it.

## Ubuntu support {#ubuntu-support}

My PPA provides packages for Ubuntu **18.04 Bionic** and **18.10 Cosmic** (read [how to install](https://github.com/yktoo/indicator-sound-switcher/blob/master/doc/install.md)). Bug reports are welcome at the [usual address](https://github.com/yktoo/indicator-sound-switcher/issues/).
