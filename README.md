# deb12_highdpi
snippets for getting enlarged font size in grub and command line for high dpi laptop displays

# grub

check if uefi or bios:

#!/bin/bash
[ -d /sys/firmware/efi ] && echo UEFI || echo BIOS


important: After disabling "Secure Boot" in BIOS, it worked.

First make a grub style font
 ```sudo grub-mkfont -o /boot/grub/fonts/DejaVuSansMonoRegular24.pf2  -s 24   /usr/share/fonts/truetype/dejavu/DejaVuSansMono.ttf```

then add the following line to /etc/default/grub

 ```GRUB_FONT="/boot/grub/fonts/DejaVuSansMonoRegular24.pf2"```

then run

```sudo update-grub```

resource: https://forums.debian.net/viewtopic.php?t=153768

3240x2160 -> fontsize 48 ?

# console

```sudo dpkg-reconfigure console-setup```

When you run it, it will ask you

Encoding: UTF-8
Character set: Guess best
Font: Try Terminus or Terminus Bold with framebuffer
Try out different fonts to see what works best for you.
