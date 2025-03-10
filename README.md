Personalized 0xfefe_0002 CTF binaries.

__NOTE__: If you are solving the 4n6-pico-XXX challenges, the description below relates to 4n6-pico-090.

# Leader board

| Placing |        Timestamp | Name |
|---------|------------------|------|
|       1 | 2025-05-03 20:02 | [FrancisHoogendijk](https://github.com/FrancisHoogendijk) |
|       2 | YYYY-MM-DD HH:MM |      |
|       3 | YYYY-MM-DD HH:MM |      |

# Request personalized challenge

To receive a binary for your pico2, you need to send us the ID of your pico2. 
To identify the ID of your pico2, you can use `picotool info -d` when it is in `BOOTSEL` mode. 
For example, the output will be something like this:

```
$ picotool info -df
Tracking device serial number C97033E01601FDC4 for reboot
The device was asked to reboot into BOOTSEL mode so the command can be executed.


Device Information
 type:                 RP2350
 package:              QFN60
 chipid:               0xc97033e01601fdc4
 flash devinfo:        0x0c00
 current cpu:          ARM
 available cpus:       ARM
 secure boot:          1
 debug enable:         1
 secure debug enable:  1
 flash size:           4096K

                       The device was asked to reboot back into application mode.
```

Send the ID to us by creating an issue in this repository of which the title is the ID of your pico2, using 

**[>>this link<<](https://github.com/0xfefe-com/0xfefe0002_ctf_binaries/issues/new/choose)**


# Flash challenge to pico2

The CTF consists of two binaries, both need to be flashed to your pico2, together. 
These can be dragged and dropped when it pops up as a storage device, or you can use `picotool` to upload them:

```
picotool reboot -f -u # to force a reboot into bootloader mode
picotool load part1.uf2
picotool reboot -f -u
picotool load part2.uf2
picotool reboot
```

# Submitting your flag

To proof you've solved the CTF, put a reply to your issue with a base64 encoded value that gives the `Verified OK` reply the following command:

```
$ echo "<YOUR BASE64 ENCODED VALUE>" | \
base64 -d | \
openssl dgst -sha256 -signature /dev/stdin \
-verify personalized/<YOUR PICO2 ID>/ec_public.pem \
flag.txt
```

