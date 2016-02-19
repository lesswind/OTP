# OTP Guide - R2.1

*While not a requirement anymore, a hardmod is still recommended.*

This guide should work without a hardmod in a relatively safe way. Thanks to the downgrades being done in emuNAND and a python script automating some of the risky edits for the New 3DS, the guide is mostly safe for use without a hardmod.

If you are going to attempt this without one, know that there may be some issues in the first couple days after the release of this revision and you should wait a while to ensure no serious errors made their way into the guide.

## Introduction

This is, to the best of my knowledge, the first public comprehensive guide to getting the console specific OTP for the 3DS.

This guide will take you through the steps of downgrading to version 2.1 to get the OTP, which was blocked from our reach with the release of 3.X (without some hardware trickery).

**This guide will work on New 3DS, Old 3DS, and 2DS in the U, E, and J regions. The C, K, and T regions shipped with version 4.X which is after the OTP lockout, and as such *cannot* downgrade far enough to use this guide.**

C, K, and T regions may be able to switch to U, E, or J temporarily but that is outside of the scope of this guide.

This guide was written by me with the process refined and software developed by the fine folks over at #Cakey on Freenode. See the bottom of this page for the full credits, this guide would not exist without them.

## FAQ

+ **Q:** *What is the OTP?*
  **A:** The OTP is a console unique region from which console specific keys seem to be derived, although it is unknown how. More info here: https://3dbrew.org/wiki/OTP_Registers
+ **Q:** *What can I do with my OTP?*
  **A:** The OTP is a requirement to use Arm9loaderhax, which gets you, among other things, 100% boot rate, emuNAND boot speed almost as fast as regular sysNAND (using something like AuReiNand), and very early Arm9 access. In the future, this will allow for running things like Decrypt9 to unbrick yourself without a hardmod and other awesome tools.
+ **Q:** *Why do we have to downgrade to get it?*
  **A:** Since version 3.0, the OTP is locked out early in sysNAND boot. There is a New 3DS only exploit that works on 9.6, but it requires extra hardware. The solution here is to downgrade emuNAND (to ensure we don't partial downgrade) to 2.1, then flash emuNAND to sysNAND to get the OTP.
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
New_3DS_Cubic_E | 7317e6ba08d69e081b82bfff818e857375259965ac0154201ea027bf766954e0
New_3DS_Cubic_J | b52047fe0bc3c7232223af4b7c55c1dbf5d32d0b74e8ad351b9be3316040c488
New_3DS_Cubic_U | 8f331d21720deac4ebfbd3f89f7d914974044d1d1fb5447bdd728ef1f8049217
New_3DS_Spider_E | 99632e7502dd956f368ee1489dc7fae3c58770cb9f16b21334b88b3d26e3d85a
New_3DS_Spider_J | 921d4bdba5eca36560e4e8cb64940a37b2fc092b31e79e259815ef8a1d734b42
New_3DS_Spider_U | 4ec17ab4f850852fa811776ff580684cd6f59a6956188421ec5d92397852302f
Old_3DS_Cubic_E | 90f0ca3ff64ad09822cb33b3387ef2fa2e2702ab39bdf7dd0c9755b17dc9f7bb
Old_3DS_Cubic_J | 6841c339eae4a3b1998abc3fd433239bbe8823f8d504159e330fe241d74035f1
Old_3DS_Cubic_U | 909cb195f375d473275ef25ad7cdf90241ddb40d2c374f3746870b4b32d0317f
Old_3DS_Spider_E | d4d9ca707f3ee1dbab323e625e19335d740b567811f52ccc660353093f6fb4b1
Old_3DS_Spider_J | f07c8c2dd118756c5b86eca2c4cbd9da37299bdee1d8c45a799d375c42135c5d
Old_3DS_Spider_U | b78380fb5653efd8fa02627b73ff9b4e41a69765175cb5b5d8c4f3f95362887b

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
+ dukesrg for hosting
+ all of #Cakey on Freenode for being awesome

*If I forgot you here, contact me and I'll add your name.*
