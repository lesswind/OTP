# OTP Guide - 2DS (Without Cubic Ninja)

This is a sub section of the main guide [here](https://github.com/Plailect/OTP/blob/master/README.md). Please read that first before continuing here.

**THIS IS COMPLETELY UNTESTED - THE ONLY AVAILABLE REGION ATM IS US**

**The steps here are the same as on the old 3ds. You must have gone through initial setup, do not format on a version below 6.0.0 or you will not be able to complete the setup process.**

## What You Need

* The 2.1 firmware pack for your region: ([U](https://mega.nz/#!IgUy1aJR!bDaYIBWLH6QePjh-buP0_SmXEwxZC0gEkKu4cbtxtNE) - [E]() - [J]()) (Mirrors: [U](https://drive.google.com/file/d/0BzPfvjeuhqoDQzdaWWtDclZmaHM/view?usp=sharing) - [E]() - [J]())
* [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases) ([Mirror](https://mega.nz/#!MgdQWYpK!CbB-EY2mPtpzHFL9Rj6GNTOpIorw6QQKdWjaL9T1H7Q)) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDazFkbG5xMTV0d1U/view?usp=sharing))
* [`arm11.bin`](https://mega.nz/#!ckcXxR4C!ISv4heZKgiIO1ZmAuk8AAxecET6SbXpW7z4PePiUlwY) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZGdKVEJUT1c0TXc/view?usp=sharing))
* [sysUpdater](https://github.com/profi200/sysUpdater/releases) ([Mirror](https://mega.nz/#!NkcEFaAD!x8mnHtm3xOrQ1fuXawGa2pipyWju6xdgaB04IyMcW3s)) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDaHUxbExoZ1dRclU/view?usp=sharing))
* [Launcher.dat QR Code](https://chart.googleapis.com/chart?cht=qr&chs=220x220&chl=http://dukesrg.no-ip.org/3ds/rop?GW147%20Safari/5373.dat%26Launcher.dat) ([Mirror](http://imgur.com/eIY7eEY)) ([Mirror](https://mega.nz/#!VgkDBIha!szD3vVQ1dwTAxx9cRG8AJYCrsLSg9IFKmsasPxHgy0E))
* Any game cart that contains an update version between 4.0 and 9.2 (See [3dsdb](http://www.3dsdb.com/) for which carts contain what updates)
* This guide assumes you are familiar with 3DS homebrew.
* This guide assumes you are on sysNAND version 9.2

## Instructions
### Section I - Prep Work
1. Download a copy of each of the things you need above and put them in a folder. The mirrors are alternate links in case the first ones do not work properly.
2. Copy Decrypt9, and sysUpdater to the `/3ds/` folder of your SD card like any other homebrew application.
3. Extract the 2.1 firmware pack for your region and place the `updates` folder on the root of your SD card.
5. From sysNAND, get into the Homebrew Launcher through the entrypoint of your choice.
6. Open Decrypt9.
7. Following the options on the main menu, backup your sysNAND and your emuNAND (if you have one) to `sysNAND.bin` and `emuNAND.bin` respectively.
10. Press (Select) on the main menu to eject your SD card
11. Put your SD card in your computer, then copy over `sysNAND.bin` and `emuNAND.bin`(if you have one) from `/Decrypt9/` to a safe location on your computer.
12. Copy **ALL** files from your SD card into a folder on your computer.
13. Reinsert your SD into your 3DS, then press (Start) to reboot into sysNAND.

### Section II - Downgrading
1. Using the entrypoint of your choice, get into the Homebrew Launcher **in sysNAND**.
2. Open sysUpdater.
3. Press (Y) to downgrade sysNAND to v2.1.
4. Reboot into sysNAND
5. If there is a black screen on reboot, try deleting the `extdata` folder in `/Nintendo 3DS/XXX/XXX/` on your SD card.

### Section III - Getting the OTP
1. Copy `arm11.bin` to the root of your SD card.
2. Go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3ds.
3. Wait for the flashes.
4. Check for a file called `a9f.bin` on the SD card. If the exploit was successful then it should exist.
5. Remove your SD card and copy `a9f.bin` to your computer.
6. Backup `a9f.bin` somewhere safe.

### Section IV - Restoring the System
1. Copy Decrypt9's `Launcher.dat` to the root of your SD card.
2. Delete all files in `/Decrypt9/`.
3. Copy your original `sysNAND.bin` and `emuNAND.bin` backups to `/Decrypt9/`.
4. Reinsert your SD card into your 3DS.
5. Boot the 3DS back up.
6. Insert your game that contains an update to a version between 4.0 and 9.2
7. Disable all network connections on the 3DS and [delete any predownloaded updates](https://gbatemp.net/threads/381489/).
8. Launch the game.
9. When prompted, press (A) to update the console.
10. When the 3DS has rebooted launch `Launcher.dat` by either scanning the QR code linked above with the camera (L and R on the home menu) or manually going to http://dukesrg.no-ip.org/3ds/ and pressing launch.
11. Following the options on the main menu, restore your sysNAND and your emuNAND from `sysNAND.bin` and `emuNAND.bin` respectively.
12. Press (Select) to eject the SD card. On your computer, delete all files on the SD card and copy over your previous backup.
13. Reinsert the SD card and reboot!
