*While not a requirement anymore, a hardmod is still recommended.*

This guide should work without a hardmod in a relatively safe way. Thanks to the downgrades being done in emuNAND and a python script automating some of the risky edits for the New 3DS, the guide is mostly safe for use without a hardmod.

If you are going to attempt this without one, know that there may be some issues in the first couple days after the release of this revision and you should wait a while to ensure no serious errors made their way into the guide.

## Introduction

This is, to the best of my knowledge, the first public comprehensive guide to getting the console specific OTP for the 3DS.

This guide will take you through the steps of downgrading to version 2.1 to get the OTP, which was blocked from our reach with the release of 3.X (without some hardware trickery).

**This guide will work on New 3DS, Old 3DS, and 2DS in the U, E, and J regions. The C, K, and T regions shipped with version 4.X which is after the OTP lockout, and as such *cannot* downgrade far enough to use this guide.**

C, K, and T regions may be able to switch to U, E, or J temporarily but that is outside of the scope of this guide.

The method for dumping the OTP without a hardmod (relatively) safely was originally created by me and was influenced by conversations with AHP_Person, Normmatt, and Vappy. The guide was based off my own personal notes you can see [here](https://www.irccloud.com/pastebin/SfsLwHWS/OTP+Notes) and was created from start to finish in about 14 days.

This guide was written by me with the process refined and software developed by the fine folks over at #Cakey on Freenode. See the bottom of this page for the full credits, this guide would not exist without them.

## Abstract

The OTP it a 0x100 byte region of seemingly random data at address 0x10012000. It is presumed that console unique keys are derived from this region, although it is currently unknown exactly how. The region is likely the console unique data store which is decrypted by the bootrom, but we don't know how that is done until somebody dumps the full protected bootrom. It is unknown at this time if anyone has successfully dumped the protected bootrom.

Prior to version 3.0.0-X, Nintendo locked access to this region using Kernel9, presumably under the assumption that an attacker would never gain access to arm9 userland (as arm9 kernel and userland are functionally identical thanks to svc 0x7B).

After version 3.0.0-X, Nintendo switched to locking this region using the register CFG_SYSPROT9, which also locks the bootloader and is set extremely early in boot, long before we are able to gain code execution. This register can be set exactly once, and cannot be switched off until the unit is fully powered off, and therefore it is impossible to dump the full OTP without a version 2.1.0-X or below.

There is, however, a method to dump the hash of the OTP on version 9.6.0-X. Because Kernel9Loader does not clear the SHA_HASH register after it has been used, dumping the SHA_HASH will give the hash of the OTP which was handed over to Kernel9 from Kernel9Loader. In addition, there is a long standing vulnerability where an MCU reboot caused by the i2c will not clear RAM like it's supposed to.

This allows for a hardware based attack where arbitrary data is written to nand_sector96+0x10 in a sysNAND backup and flashed to the device. Afterwards we wire the i2c to MCU reboot on our command, write a payload (which will write 0x1000A040 - 0x1000A060 to a file on the SD card) to arm9 memory somewhere, fill all memory a NOP sled followed by a JMP instruction pointing to the payload. We can then MCU reboot repeatedly (incrementing nand_sector96+0x10 by 1 each time) until the Kernel9Loader jumps to the payload by random chance.

Because of the complexity and extra hardware involved in the method described above, I have decided to limit the scope of this guide strictly to the software based approach of downgrading to a version below 3.0.0-X. Version 2.1.0-X was selected because it is the only version below 3.0.0-X that contains a fully exploitable browser version (2.0.0-X has a partially exploitable browser, but it won't work for other reasons).

This guide will take you through the process of downgrading you emuNAND to 2.1.0-X to ensure you do not get a partial downgrade (which is when some titles are on one version and others are on a different version) which are difficult to recover from. On the New 3DS you must then decrypt with your console's 0x5 xorpad (which is New 3DS only) and then reencrypt with your console's 0x4 xorpad. Afterwards you overwrite the New 3DS's NAND NCSD (the header that specifies each partition's location) with the NCSD from an Old 3DS and flash the emuNAND to sysNAND. These steps are unneeded on an Old 3DS.

## FAQ / TL;DR

+ **Q:** *What is the OTP?*
  **A:** The OTP is a console unique region from which console specific keys seem to be derived, although it is unknown how. More info here: https://3dbrew.org/wiki/OTP_Registers
+ **Q:** *What can I do with my OTP?*
  **A:** The OTP is a requirement to use Arm9loaderhax, which gets you, among other things, 100% boot rate, emuNAND boot speed almost as fast as regular sysNAND (using something like AuReiNand), and very early Arm9 access. In the future, this will allow for running things like Decrypt9 to unbrick yourself without a hardmod and other awesome tools.
+ **Q:** *Why do we have to downgrade to get it?*
  **A:** Since version 3.0, the OTP is locked out early in sysNAND boot. There is a New 3DS only exploit that works on 9.6, but it requires extra hardware. The solution we are using is to downgrade emuNAND (to ensure we don't partial downgrade) to 2.1, then flash emuNAND to sysNAND to get the OTP.
+ **Q:** *What version do I have to be on?*
  **A:** You must be on version 9.2 or less but this guide assumes 9.2. Any lower version may work but you're on your own for that.
+ **Q:** *What's the current brick rate?*
  **A:** Bricks are still possible due to either bad software or user error, although they are less common than before. If you have a comfortable traditional emuNAND setup right now then I would recommended staying with it until Arm9loaderhax has more uses.

## Get Started

*Click the appropriate link below:*

New 3DS | Old 3DS / 2DS
:---: | :---:
[With Cubic Ninja](https://github.com/Plailect/OTP/blob/master/New_3DS_Cubic.md) | [With Cubic Ninja](https://github.com/Plailect/OTP/blob/master/Old_3DS_Cubic.md)
[Without Cubic Ninja](https://github.com/Plailect/OTP/blob/master/New_3DS_Spider.md) | [Without Cubic Ninja](https://github.com/Plailect/OTP/blob/master/Old_3DS_Spider.md)

Pack .zip | SHA-256
:---: | :---:
New_3DS_Cubic_E | 3efa999e5ca14287bd8aa2a5037654c3edca7c55728b5cd632eb4a2d08b50437
New_3DS_Cubic_J | 6e21864097edc535b4d22f22fc56c8eb46ec14c47791a6f3723a87bc964ec171
New_3DS_Cubic_U | b163cce870ddafc6097f72ca32a117097e4f84b84cfc1e07a01252305a56f38f
New_3DS_Spider_E | 2ed4b7f2b3fba41e9a65f8946e289118d1a9f5111832f7fe15403a3e736f2ac9
New_3DS_Spider_J | 64808b3dc04f13c7a7951b41c4949e01d5162e8544edb1e4ffd5399b1031ab06
New_3DS_Spider_U | 81516004b42e51b9eec6bcecd38c5d4f90e1216e0a7e0dc97fafe2194f5ae6c9
Old_3DS_Cubic_E | 7a41faff8361533d370f8e717fcc42e0ae789627fa305101476250c90ec1a2ab
Old_3DS_Cubic_J | 51371a4f6d0007e3218489c21104261b2e7dde75a98fda92185f3ce336923576
Old_3DS_Cubic_U | 2ba6c0a14374e237e6d220bcbd84b8794c4dc045b5c0723912e853ff8d393a9c
Old_3DS_Spider_E | 586ded077063f6c27d270f8df14535a7ccd326d595a304321764b236ddafe403
Old_3DS_Spider_J | a408a98796d40bda44b0620af993c65ead27945c422dbd877bb3cc309e5e792f
Old_3DS_Spider_U | d32be7bad321773aae4d5c4b8bc87c2beb84531bef7f8cb9f1266a947079d417

## Credits

+ AHP_Person for code.bin
+ Normmatt for load.bin
+ yellows8 for answering my questions
+ b1l1s (he's back baby) for being fucking amazing
+ mid-kid for letting us use his channel
+ Gelex for being fucking amazing
+ dank101 for testing
+ Vappy for emotional support
+ MassExplosion123 for answering questions
+ Psi-Hate for testing
+ Shadowtrance for answering questions and testing
+ icecream for testing
+ s_99 for emotional support
+ dark_samus for testing
+ Urbanshadow for fixing my python script
+ Mrrraou for helping with support
+ dukesrg for hosting 2xrsa
+ all of #Cakey on Freenode for being awesome

*If I forgot you here, contact me and I'll add your name.*
