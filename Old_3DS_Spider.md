# OTP Guide - Old 3DS / 2DS (Without Cubic Ninja)

This is a sub section of the main guide [here](https://github.com/Plailect/OTP/blob/master/README.md). Please read that first before continuing here.

**All regions are now available!**

**The steps for 2DS are the same as on the old 3ds, except for that you must have gone through initial setup. Do not format a 2DS on a version below 6.0.0 or you will not be able to complete the setup process.**

## What You Need

* The all-in-one pack for your region: ([U](https://github.com/Plailect/OTP/archive/Old_3DS_Spider_U.zip) - [E](https://github.com/Plailect/OTP/archive/Old_3DS_Spider_E.zip) - [J](https://github.com/Plailect/OTP/archive/Old_3DS_Spider_J.zip))
* [Python 3.5.1](https://www.python.org/downloads/)
* This guide assumes you are familiar with 3DS homebrew.
* This guide assumes you are on sysNAND version 9.2
* This guide assumes you have a working emuNAND and CFW (such as [CakesFW](https://github.com/mid-kid/CakesForeveryWan), [ReiNand](https://github.com/Reisyukaku/ReiNand), or [rxTools](https://github.com/roxas75/rxTools)).

## Instructions
### Section I - Prep Work
1. Download the all-in-one pack `.zip` for your region.
2. Extract the `Old_3DS_Spider_[U/E/J]/` folder from the `.zip` to somewhere on your computer.
1. Delete any existing `Updates` folder on your sdcard that may be leftover from a previous downgrade.
3. Copy all files from `Old_3DS_Spider_[U/E/J]/Section_I/Copy_To_SD_Card/` to your SD card. Replace any existing files.
5. From sysNAND, get into the Homebrew Launcher through the entrypoint of your choice.
6. Open Decrypt9.
7. Following the options on the main menu, backup your sysNAND and your emuNAND to `sysNAND.bin` and `emuNAND.bin` respectively.
8. From Decrypt9's main menu, select "XORpad Generator Options."
9. Follow the options to dump "CTRNAND Padgen" to `nand.fat16.xorpad`.
10. Press (Select) on the main menu to eject your SD card.
11. Put your SD card in your computer, then copy over `sysNAND.bin`, `emuNAND.bin`, and `nand.fat16.xorpad` from the root of your SD card to `Old_3DS_Spider_[U/E/J]/Section_I/Backup/`.
13. Delete `sysNAND.bin`, `emuNAND.bin`, and `nand.fat16.xorpad` from the root of your SD card, then reinsert into your 3DS.
18. Copy all files from your SD card into `Old_3DS_Spider_[U/E/J]/Section_I/Backup/SD_Backup` on your computer.

(Yes I know you don't need your xorpad, but it's good practice to have a way to decrypt your backups!)

### Section II - Downgrading
3. Copy all files from `Old_3DS_Spider_[U/E/J]/Section_II/Copy_To_SD_Card/` to your SD card. Replace any existing files.
1. Boot your 3DS into emuNAND using the CFW of your choice.
2. **If you are on 2DS, make sure your wifi is on, you will not be able to toggle it in 2.1.**
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
8. Copy `emuNAND_formatted.bin` from the root of your SD card to `Old_3DS_Spider_[U/E/J]/Section_I/Backup/`
7. Open sysUpdater **on emuNAND**.
8. Press (Y) to downgrade emuNAND to v2.1.
9. If you encounter an error at any point during the downgrade, restore your emuNAND backup to emuNAND by copying `Old_3DS_Spider_[U/E/J]/Section_I/Backup/emuNAND_formatted.bin` to the root of your SD card and restoring using decrypt9 through homebrew menu on sysNAND. Afterwards, you can retry the downgrade on emuNAND, restoring from backup whenever it fails, until it goes through successfully.
10. 10. If you still are having issues, some users have reported upgrading **emuNAND** to 10.5 then downgrading may work. This is because this update will remove any modified TWL_FIRM which sysUpdater has trouble dealing with.
10. Once you have successfully downgraded emuNAND with no errors, reboot into sysNAND **(No current CFW can boot a 2.1 emuNAND)** and get into the Homebrew Launcher through the entrypoint of your choice.
10. Open Decrypt9.
11. Following the options on the main menu, backup your emuNAND to `emuNAND.bin`.
12. Press (Select) on the main menu to eject your SD card, then rename `emuNAND.bin` to `sysNAND.bin` on the root of your SD card from your computer.
13. Reinsert your SD card into your 3DS and press (B).
25. Following the options on the main menu, restore your sysNAND from `sysNAND.bin`.
26. Cross your fingers.
27. Reboot.
28. If there is a black screen on reboot, try deleting the `extdata` folder in `/Nintendo 3DS/XXX/XXX/` on your SD card or booting with the SD card out and reinserting it after boot.

### Section III - Getting the OTP
1. Copy all files from `Old_3DS_Spider_[U/E/J]/Section_III/Copy_To_SD_Card/` to your SD card. Replace any existing files.
2. Go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3ds.
3. Wait for the flashes. You can power off after about ten seconds of flashing.
4. Check for a file named `a9f.bin` on the SD card. If the exploit was successful then it should be `256 Bytes`.
5. Remove your SD card and copy `a9f.bin` to your computer.
6. Rename `a9f.bin` to `OTP.bin`.
7. Backup `OTP.bin` somewhere safe.

### Section IV - Restoring the System
1. Copy all files from `Old_3DS_Spider_[U/E/J]/Section_IV/Copy_To_SD_Card/` to your SD card. Replace any existing files.
1. Delete any sysNAND or emuNAND `.bin` files from the root of your SD card.
2. Copy `sysNAND.bin` and `emuNAND.bin` from `Old_3DS_Spider_[U/E/J]/Section_I/Backup/` to the root of your SD card.
3. Rename `sysNAND.bin` to `NAND.bin` on your SD card.
3. Reinsert your SD card and go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3ds.
4. After Decrypt9 has loaded, follow the options on the main menu to restore your sysNAND and your emuNAND from `sysNAND.bin` and `emuNAND.bin` respectively.
5. Shut down your 3DS and delete all files on the SD card using your computer. *(Do not format.)*
6. Copy all files from `Old_3DS_Spider_[U/E/J]/Section_I/Backup/SD_Backup` to your SD card.
7. Reinsert the SD card and reboot!
