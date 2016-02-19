# OTP Guide - New 3DS (With Cubic Ninja)

This is a sub section of the main guide [here](https://github.com/Plailect/OTP/blob/master/README.md). Please read that first before continuing here.

**All regions are now available!**

## What You Need

* The all-in-one pack for your region: ([U](https://github.com/Plailect/OTP/archive/New_3DS_Cubic_U.zip) - [E](https://github.com/Plailect/OTP/archive/New_3DS_Cubic_E.zip) - [J](https://github.com/Plailect/OTP/archive/New_3DS_Cubic_J.zip))
* [Cubic Ninja](http://www.amazon.com//dp/B004SG211I)
* [Python 3.5.1](https://www.python.org/downloads/)
* This guide assumes you are familiar with 3DS homebrew.
* This guide assumes you are on sysNAND version 9.2
* This guide assumes you have a working emuNAND and CFW (such as [CakesFW](https://github.com/mid-kid/CakesForeveryWan), [ReiNand](https://github.com/Reisyukaku/ReiNand), or [rxTools](https://github.com/roxas75/rxTools)).

## Instructions
### Section I - Prep Work
1. Download the all-in-one pack `.zip` for your region.
2. Extract the `New_3DS_Cubic_[U/E/J]/` folder from the `.zip` to somewhere on your computer.
3. Copy all files from `New_3DS_Cubic_[U/E/J]/Section_I/Copy_To_SD_Card/` to your SD card. Replace any existing files.
5. From sysNAND, get into the Homebrew Launcher through the entrypoint of your choice.
6. Open Decrypt9.
7. Following the options on the main menu, backup your sysNAND and your emuNAND to `sysNAND.bin` and `emuNAND.bin` respectively.
8. From Decrypt9's main menu, select "XORpad Generator Options."
9. Follow the options to dump "CTRNAND Padgen" to `nand.fat16.xorpad`.
10. Press (Select) on the main menu to eject your SD card.
11. Put your SD card in your computer, then rename `nand.fat16.xorpad` to `nand.fat16_0x5_.xorpad` on the root of your SD card.
12. Copy over `sysNAND.bin`, `emuNAND.bin`, and `nand.fat16_0x5_.xorpad` from the root of your SD card to `New_3DS_Cubic_[U/E/J]/Section_I/Backup/`.
13. Delete `sysNAND.bin`, `emuNAND.bin`, and `nand.fat16_0x5_.xorpad` from the root of your SD card, then reinsert into your 3DS.
14. Press (B) then go to "XORpad Generator Options" once more. Follow the options to dump "CTRNAND Padgen 0x4" to `nand.fat16.xorpad`.
10. Press (Select) on the main menu to eject your SD card.
11. Put your SD card in your computer, then rename `nand.fat16.xorpad` to `nand.fat16_0x4_.xorpad` on the root of your SD card.
12. Copy over `nand.fat16_0x4_.xorpad` from the root of your SD card to `New_3DS_Cubic_[U/E/J]/Section_I/Backup/`.
13. Delete `nand.fat16_0x4_.xorpad` from the root of your SD card.
18. Copy all files from your SD card into `New_3DS_Cubic_[U/E/J]/Section_I/Backup/SD_Backup` on your computer.

### Section II - Downgrading
3. Copy all files from `New_3DS_Cubic_[U/E/J]/Section_II/Copy_To_SD_Card/` to your SD card. Replace any existing files.
1. Boot your 3DS into emuNAND using the CFW of your choice.
2. **Make sure your wifi is on, you will not be able to toggle it in 2.1.**
2. Using the CIA Manager of your choice of your choice, install TinyFormat.cia **on emuNAND**.
3. Open TinyFormat **on emuNAND**.
4. Press (Y) to format emuNAND.
5. Reboot back into emuNAND and complete initial setup *without* linking NNID.
6. After reinstalling the CIA Manager of your choice, install SysUpdater.cia **on emuNAND**.
6. Reboot into sysNAND, then get into the Homebrew Launcher through the entrypoint of your choice.
6. Open Decrypt9.
7. Following the options on the main menu, backup your emuNAND to `emuNAND.bin`.
10. Press (Select) on the main menu to eject your SD card
11. Put your SD card in your computer, then rename `emuNAND.bin` on the root of your SD card to `emuNAND_formatted.bin`.
8. Copy `emuNAND_formatted.bin` from the root of your SD card to `New_3DS_Cubic_[U/E/J]/Section_II/Backup/`
7. Open sysUpdater **on emuNAND**.
8. Press (Y) to downgrade emuNAND to v2.1.
9. If you encounter an error at any point during the downgrade, restore your emuNAND backup to emuNAND by copying `New_3DS_Cubic_[U/E/J]/Section_I/Backup/emuNAND_formatted.bin` to the root of your SD card and restoring using decrypt9 through homebrew menu on sysNAND. Afterwards, you can retry the downgrade on emuNAND, restoring from backup whenever it fails, until it goes through successfully.
9. Reboot into sysNAND **(emuNAND will be bricked by the downgrade)** and get into the Homebrew Launcher through the entrypoint of your choice.
10. Open Decrypt9.
11. Following the options on the main menu, backup your emuNAND to `emuNAND.bin`.
12. Press (Select) on the main menu to eject your SD card, then rename `emuNAND.bin` to `emuNAND_bricked.bin` on the root of your SD card from your computer.
13. Copy over `emuNAND_bricked.bin` to `New_3DS_Cubic_[U/E/J]/Section_II/Bricked/` on your computer.
13. Double click either `Windows.py` if you are on Windows, or `LinuxOrMac.py` if you are on Linux ~~or Mac~~ (**Mac is broken, wait for a fix**).
14. Wait.
22. Copy the modified `sysNAND.bin` that was just created from `New_3DS_Cubic_[U/E/J]/Section_II/Bricked/Unbricked/` to the root of your SD card.
24. Reinsert your SD card into your 3DS and press (B).
25. Following the options on the main menu, restore your sysNAND from `sysNAND.bin`.
26. Cross your fingers.
27. Reboot.
28. If there is a black screen on reboot, try deleting the `extdata` folder in `/Nintendo 3DS/XXX/XXX/` on your SD card or booting with the SD card out and reinserting it after boot.

### Section III - Getting the OTP
1. Copy all files from `New_3DS_Cubic_[U/E/J]/Section_III/Copy_To_SD_Card/` to your SD card. Replace any existing files.
1. Open Cubic Ninja.
2. Select "Create", then "QR Code", then "Scan QR Code."
3. Scan the QR code `New_3DS_Cubic_[U/E/J]/Section_II/Cubic_Ninja_Qr_Code.png`
4. Check your `OTP.bin` on the SD card. If the exploit was successful then it should **not** be `0 Bytes`.
5. Remove your SD card and copy `OTP.bin` to your computer.
6. Backup `OTP.bin` somewhere safe.

### Section IV - Restoring the System
1. Copy all files from `New_3DS_Cubic_[U/E/J]/Section_IV/Copy_To_SD_Card/` to your SD card. Replace any existing files.
1. Delete any sysNAND or emuNAND `.bin` files from the root of your SD card.
2. Copy `sysNAND.bin` and `emuNAND.bin` from `New_3DS_Cubic_[U/E/J]/Section_I/Backup/` to the root of your SD card.
3. Reinsert your SD card and go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3ds.
4. After Decrypt9 has loaded, follow the options on the main menu to restore your sysNAND and your emuNAND from `sysNAND.bin` and `emuNAND.bin` respectively.
5. Shut down your 3DS and delete all files on the SD card using your computer. *(Do not format.)*
6. Copy all files from `New_3DS_Cubic_[U/E/J]/Section_I/Backup/SD_Backup` to your SD card.
7. Reinsert the SD card and reboot!
