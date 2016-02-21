Installing Raspbian Operating System Images Using Mac OS
========================================================

There are many ways to write the Raspbian disk image to the SD card. Below is the tried and true method we think is the easiest. Disagree... let us know or send a pull request.

### (Mostly) graphical interface

- Connect the SD card reader with the SD card inside. Note that it must be formatted in FAT32.
- From the Apple menu, choose About This Mac, then click on More info...; if you are using Mac OS X 10.8.x Mountain Lion or newer then click on System Report.
- Click on USB (or Card Reader if using a built-in SD card reader) then search for your SD card in the upper right section of the window. Click on it, then search for the BSD name in the lower right section; it will look something like 'diskn' where n is a number (for example, disk4). Make sure you take a note of this number.
- Unmount the partition so that you will be allowed to overwrite the disk; to do this, open Disk Utility and unmount it (do not eject it, or you will have to reconnect it). Note that On Mac OS X 10.8.x Mountain Lion, "Verify Disk" (before unmounting) will display the BSD name as "/dev/disk1s1" or similar, allowing you to skip the previous two steps.
- From the terminal run:

    ```
    sudo dd bs=1m if=path_of_your_image.img of=/dev/rdiskn
    ```

    Remember to replace `n` with the number that you noted before!

   - If this command fails, try using `disk` instead of `rdisk`:

       ```
       sudo dd bs=1m if=path_of_your_image.img of=/dev/diskn
       ```

*This guide uses content from the Raspberry Pi Foundation page
[Installing Operating System Images on Mac OS](https://www.raspberrypi.org/documentation/installation/installing-images/mac.md), which is shared under the [Creative Commons Attribution-ShareAlike 4.0 license](http://creativecommons.org/licenses/by-sa/4.0/)*

---
[< Back](raspberry-pi-first-setup.md) - Raspberry Pi First Setup
