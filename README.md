# dwm-mackeys
Adds functionality to function keys on MacBook Pros

## Installation
The patch assumes a fresh copy of dwm. Beyond that, you may have to edit the source code by hand.
In the root directory, run this command:
```
patch -b < /path/to/dwm-mackeys-version.diff
```
That's it. If anything failed, then fire up your preferred editor and get those hands dirty.

## Requirements
* For the media control buttons, install `mocp`.
* For screen and keyboard backlight control, install the appropriate driver. For me, it is [`nvidia-bl`](https://aur.archlinux.org/packages/nvidia-bl/) from the AUR. If you have a different driver, you might need to change the device that xbacklight controls in your `config.def.h`/`config.h`.
* Add these lines to your sudoers file:
	* `user host= NOPASSWD: /usr/bin/xbacklight -ctrl smc*`
	* `user host= NOPASSWD: /usr/bin/xbacklight -ctrl nvidia_backlight -*`
	* where `user` is your username and `host` is the hostname of your computer (which you can find in /etc/hostname). Again, you might need to change the device name (`smc` and `nvidia_backlight`). Don't forget the trailing dash in the second line before the wildcard asterisk.

### Author
Hilde N.
