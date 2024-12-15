Personalized 0xfefe_0002 CTF binaries.

To identify the ID of your pico2, you can use `picotool info -d` when it is in `BOOTSEL` mode. To get your personalized binary uploaded here, drop an email with your pico2 ID to 
[ctf@0xfefe.com](mailto:ctf@0xfefe.com?subject=0xfefe_0002%20CTF%20Pico2%20ID&body=Insert%20Pico2%20ID%20%3CHERE%3E)


The CTF consists of two parts, both need to be flashed to your pico2, together. These can be dragged and dropped when it pops up as a storage device, or you can use `picotool` to upload them:

```
picotool reboot -f -u # to force a reboot into bootloader mode
picotool load part1.uf2
picotool reboot -f -u
picotool load part2.uf2
picotool reboot
```