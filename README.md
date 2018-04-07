# Fast Track Ultra (FTU)

Using the FTU under Linux isn't trivial. Although there are several sites on the topic out-there, it appears
that none of what I could fine really suited my requirements which are, hopefully, not that exotic.

This repo will store my notes, scripts, dot files and manuals to actually make it work.

### About the device
- It is a legacy device;
- It is a decent [prosumer sound interface](https://www.soundonsound.com/reviews/m-audio-fast-track-ultra);
- It's [flexible enough for me](http://akmedia.digidesign.com/support/compressed/Fast_Track_Ultra_Hookups_77639.pdf);
- It's no longer supported on modern macOS but is recognized by Linux's [ALSA project](https://www.alsa-project.org/main/index.php/Matrix:Vendor-MAudio);
- I still have a unit which works great. The day it dies, this repository will become obsolete.

## Requirements
- The 4 acoustic inputs on the front and the 6 acoustic inputs on the back should be recognized as independant mono channels;
- The outputs 1-2 on the back should be considered as the only outputs for mainstream applications (stereo profile, instead of surround);
- All other audio outputs should be available to studio tools;
- Whatever tooling is necessary to make it work, it should work for all profiles on the system, so kids can play games with sound.

## The out-of-the-box experience with Linux (all versions, 2018)
- The soundcard is indeed recognized by ALSA 
- alsa(-lib?) provides a bunch of surround profiles for that soundcard, has it features multiple outputs (mostly useless for musicians)
- PulseAudio automagically selects `surround71` speaker profile and the sound from the stereo monitors is awful.

## Comments so far

### Configuring ALSA (`.asoundrc`) is painful
- it is as much fun as configuring sendmail and ElasticSearch;
- the documentation is somewhat opaque;
- most examples out there are irrelevant to studio setups, and poorly documented;
- no visual front-end or templates to help build one although some samples are available under `/usr/share/alsa`
