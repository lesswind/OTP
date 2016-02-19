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

Pack | SHA-256
:---: | :---:
New_3DS_Cubic_U | ~~d365b7c952ebe767e81ac2ce7ccf30cc4b0442c28b0871b8a03657f7deb3af13~~
New_3DS_Cubic_E | ~~fc0e59728f1096fd65d5d1bfc25232f1993154c4916e8a9a26232e30a1718812~~
New_3DS_Cubic_J | ~~4ac3018593db6a08c5dd4c6309c5d1f6d95a7fe64d4f447e8956980543691577~~
Old_3DS_Cubic_U | ~~3ec9823a8a8bde427ee6622ca54f9d2c15abc7975eb45925ade3b7ca74d9504b~~
Old_3DS_Cubic_E | ~~f4482ce9eea77a6c89d84237d49c0a647b12961e07d4d77f037a87bbb9121612~~
Old_3DS_Cubic_J | ~~0c43a5da1ae0fbc799b2ca0467196989251b7d9f489236efb5802b7fead72c07~~
New_3DS_Spider_U | ~~d2969a406337c5c15c044d6cbb9feb55fa54b169a282f6b331b4afcf1052a298~~
New_3DS_Spider_E | ~~5907913920a19380702bd3f5c21a8f81fe4906ae4186a3268cb865e7fcb835ec~~
New_3DS_Spider_J | ~~60c8fc76370e3a19cd2c26d20f0d02553c57635bd748c4f2b51fdf79d43d3644~~
Old_3DS_Spider_U | ~~755b2b761a7163d79b5dd6b6499b24ad9137d447a6c8719dacd68799a24bfa68~~
Old_3DS_Spider_E | ~~e5c742fe8819aefaddb40d5869f91bdf5ba7c4b4e1dc09a2a0f1a1982aaafe78~~
Old_3DS_Spider_J | ~~755b2b761a7163d79b5dd6b6499b24ad9137d447a6c8719dacd68799a24bfa68~~

**The SHA-256s are outdated!**


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
+ dukesrg for hosting
+ all of #Cakey on Freenode for being awesome

*If I forgot you here, contact me and I'll add your name.*
