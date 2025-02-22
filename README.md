# About this experimental version feat by F4HWN

Based on Egzumer v0.22,

- improve default power settings level (Low ~125mW, Mid ~2W and High ~5W),
- improve s-meter (IARU recommandations),
- improve UI (menu, s-meter, MAIN ONLY mode, RX blink, RX LED blink, Squelch level, Mon, etc.),
- add SetLow menu to set low power (<20mW, 125mW, 250mW, 500mW and 1W),
- add SetPtt menu to set PTT mode (Classic or OnePush),
- add SetTot menu to set TOT alert (Off, Sound, Visual, All),
- add SetCtr menu to set contrast (0 to 15),
- add SetInv menu to set screen in invert mode (On or Off),
- add SetEot menu to set EOT (End Of Transmission) alert (Off, Sound, Visual, All),
- add SetMet menu to set s-meter style (Classic or Tiny),
- add SetLck menu to set what is locked (Keys or Keys + PTT),
- add SetGui menu to set font size on the VFO baseline (Classic or Tiny),
- add SetPtt mode in status bar,
- add VFO number on MAIN ONLY mode,
- add actions SWITCH RxMode, SWITCH PTT, SWITCH WIDE NARROW and 1750Hz,
- add the F + UP or F + DOWN key combination to dynamically change the Squelch level,
- add many fix (squelch, s-meter and DTMF overlaying, scan list 2 ignored, etc.),
- remove KeyLock message,
- enabled ENABLE_CTCSS_TAIL_PHASE_SHIFT,
- disabled ENABLE_DTMF_CALLING,
- disabled SCRAMBLER,
- special process to unlock TX on all bands needs only to be repeat 3 times,
- and more...

As usual, you can use [online flasher](https://egzumer.github.io/uvtools/?firmwareURL=https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/raw/main/firmware.packed.bin).


> [!NOTE]
About SetPtt menu, if you select the OnePush option, you no longer need to press the PTT continuously to transmit. Simply press once to start transmission, and press a second time to stop. No more finger cramps :)

> [!WARNING]
> EN - Use this firmware at your own risk (entirely). There is absolutely no guarantee that it will work in any way shape or form on your radio(s), it may even brick your radio(s), in which case, you'd need to buy another radio.
Anyway, have fun.
>
> _FR - Utilisez ce firmware à vos risques et périls. Il n'y a absolument aucune garantie qu'il fonctionnera d'une manière ou d'une autre sur votre (vos) radio(s), il peut même bousiller votre (vos) radio(s), dans ce cas, vous devrez acheter une autre radio. Quoi qu'il en soit, amusez-vous bien._

> [!CAUTION]
> EN - I recommend to backup your eeprom with [k5prog](https://github.com/sq5bpf/k5prog) before playing with alternative firmwares. It's a good reflex to have. 
>
> _FR - Je recommande de sauvegarder votre eeprom avec [k5prog](https://github.com/sq5bpf/k5prog) avant de jouer avec des firmwares alternatifs. C'est un bon réflexe à avoir._

# Old versions

You can find all the older versions of my modified firmware in the [archive](https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/tree/main/archive) directory.

# Some photos

Here are a few photos.

|![SetPtt Option](https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/blob/main/photos/IMG_3080.jpeg)|
|:--:|
| SetPtt Option |


|![Dual RX Respond](https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/blob/main/photos/IMG_3082.jpeg)|
|:--:|
| Dual RX Respond |


|![Main Only](https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/blob/main/photos/IMG_3081.jpeg)|
|:--:|
| Main Only |


|![Main TX Dual RX](https://github.com/armel/uv-k5-firmware-custom-feat-F4HWN/blob/main/photos/IMG_3079.jpeg)|
|:--:|
| Main TX Dual RX |

# About enabled/disabled compile options of this experimental version feat by F4HWN

Here are the full settings,

```
ENABLE_CLANG                  := 0     **experimental, builds with clang instead of gcc (LTO will be disabled if you enable this)
ENABLE_SWD                    := 0       only needed if using CPU's SWD port (debugging/programming)
ENABLE_OVERLAY                := 0       cpu FLASH stuff, not needed
ENABLE_LTO                    := 1     **experimental, reduces size of compiled firmware but might break EEPROM reads (OVERLAY will be disabled if you enable this)

ENABLE_UART                   := 1       without this you can't configure radio via PC !
ENABLE_AIRCOPY                := 0       easier to just enter frequency with butts
ENABLE_FMRADIO                := 1       WBFM VHF broadcast band receiver
ENABLE_NOAA                   := 0       everything NOAA (only of any use in the USA)
ENABLE_VOICE                  := 0       want to hear voices ?
ENABLE_VOX                    := 1
ENABLE_ALARM                  := 0       TX alarms
ENABLE_TX1750                 := 0       side key 1750Hz TX tone (older style repeater access)
ENABLE_PWRON_PASSWORD         := 0       power-on password stuff
ENABLE_DTMF_CALLING           := 0       DTMF calling fuctionality, sending calls, receiving calls, group calls, contacts list etc.
ENABLE_FLASHLIGHT             := 1       enable top flashlight LED (on, blink, SOS)

ENABLE_BIG_FREQ               := 1       big font frequencies (like original QS firmware)
ENABLE_SMALL_BOLD             := 1       bold channel name/no. (when name + freq channel display mode)
ENABLE_KEEP_MEM_NAME          := 1       maintain channel name when (re)saving memory channel
ENABLE_WIDE_RX                := 1       full 18MHz to 1300MHz RX (though front-end/PA not designed for full range)
ENABLE_TX_WHEN_AM             := 0       allow TX (always FM) when RX is set to AM
ENABLE_F_CAL_MENU             := 0       enable the radios hidden frequency calibration menu
ENABLE_CTCSS_TAIL_PHASE_SHIFT := 1       standard CTCSS tail phase shift rather than QS's own 55Hz tone method
ENABLE_BOOT_BEEPS             := 0       gives user audio feedback on volume knob position at boot-up
ENABLE_SHOW_CHARGE_LEVEL      := 1       show the charge level when the radio is on charge
ENABLE_REVERSE_BAT_SYMBOL     := 0       mirror the battery symbol on the status bar (+ pole on the right)
ENABLE_NO_CODE_SCAN_TIMEOUT   := 1       disable 32-sec CTCSS/DCS scan timeout (press exit butt instead of time-out to end scan)
ENABLE_AM_FIX                 := 1       dynamically adjust the front end gains when in AM mode to help prevent AM demodulator saturation, ignore the on-screen RSSI level (for now)
ENABLE_AM_FIX_SHOW_DATA       := 0       show debug data for the AM fix
ENABLE_SQUELCH_MORE_SENSITIVE := 1       make squelch levels a little bit more sensitive - I plan to let user adjust the values themselves
ENABLE_FASTER_CHANNEL_SCAN    := 1       increases the channel scan speed, but the squelch is also made more twitchy
ENABLE_RSSI_BAR               := 1       enable a dBm/Sn RSSI bar graph level in place of the little antenna symbols
ENABLE_AUDIO_BAR              := 1       experimental, display an audio bar level when TX'ing
ENABLE_COPY_CHAN_TO_VFO       := 1       copy current channel into the other VFO. Long press `1 BAND` when in channel mode
ENABLE_SPECTRUM               := 1       fagci spectrum analyzer, activated with `F` + `5 NOAA`
ENABLE_REDUCE_LOW_MID_TX_POWER:= 0       makes medium and low power settings even lower
ENABLE_FEAT_F4HWN             := 1       changes by F4HWN 
ENABLE_BYP_RAW_DEMODULATORS   := 0       additional BYP (bypass?) and RAW demodulation options, proved not to be very useful, but it is there if you want to experiment
ENABLE_BLMIN_TMP_OFF          := 0       additional function for configurable buttons that toggles `BLMin` on and off wihout saving it to the EEPROM
ENABLE_SCAN_RANGES            := 1       scan range mode for frequency scanning, see wiki for instructions (radio operation -> frequency scanning)
```

> [!IMPORTANT]
Be aware. I choosed to disable ENABLE_DTMF_CALLING. I started to run out of memory, and I believe this option has little relevance to our amateur radio activities. One must know how to compromise. This allowed me to free up 6% of memory, which is significant. It will be useful for me to be able to develop other things.

# Open re-implementation of the Quansheng UV-K5/K6/5R v2.1.27 firmware

This repository is a merge of [OneOfEleven custom firmware](https://github.com/OneOfEleven/uv-k5-firmware-custom) with [fagci spectrum analizer](https://github.com/fagci/uv-k5-firmware-fagci-mod/tree/refactor) plus my few changes.<br>
All is a cloned and customized version of DualTachyon's open firmware found [here](https://github.com/DualTachyon/uv-k5-firmware) ... a cool achievement !

> [!WARNING]  
> Use this firmware at your own risk (entirely). There is absolutely no guarantee that it will work in any way shape or form on your radio(s), it may even brick your radio(s), in which case, you'd need to buy another radio.
Anyway, have fun.

## Table of Contents

* [Main Features](#main-features)
* [Manual](#manual)
* [Radio Performance](#radio-performance)
* [User Customization](#user-customization)
* [Compiler](#compiler)
* [Building](#building)
* [Credits](#credits)
* [Other sources of information](#other-sources-of-information)
* [License](#license)
* [Example changes/updates](#example-changesupdates)

## Main features:
* many of OneOfEleven mods:
   * AM fix, huge improvement in reception quality
   * long press buttons functions replicating F+ action
   * fast scanning
   * channel name editing in the menu
   * channel name + frequency display option
   * shortcut for scan-list assignment (long press `5 NOAA`)
   * scan-list toggle (long press `* Scan` while scanning)
   * configurable button function selectable from menu
   * battery percentage/voltage on status bar, selectable from menu
   * longer backlight times
   * mic bar
   * RSSI s-meter
   * more frequency steps
   * squelch more sensitive
* fagci spectrum analyzer (**F+5** to turn on)
* some other mods introduced by me:
   * SSB demodulation (adopted from fagci)
   * backlight dimming
   * battery voltage calibration from menu
   * better battery percentage calculation, selectable for 1600mAh or 2200mAh
   * more configurable button functions
   * long press MENU as another configurable button
   * better DCS/CTCSS scanning in the menu (`* SCAN` while in RX DCS/CTCSS menu item)
   * Piotr022 style s-meter
   * restore initial freq/channel when scanning stopped with EXIT, remember last found transmission with MENU button
   * reordered and renamed menu entries
   * LCD interference crash fix
   * many others...

 ## Manual

Up to date manual is available in the [Wiki section](https://github.com/egzumer/uv-k5-firmware-custom/wiki)

## Radio performance

Please note that the Quansheng UV-Kx radios are not professional quality transceivers, their
performance is strictly limited. The RX front end has no track-tuned band pass filtering
at all, and so are wide band/wide open to any and all signals over a large frequency range.

Using the radio in high intensity RF environments will most likely make reception anything but
easy (AM mode will suffer far more than FM ever will), the receiver simply doesn't have a
great dynamic range, which results in distorted AM audio with stronger RX'ed signals.
There is nothing more anyone can do in firmware/software to improve that, once the RX gain
adjustment I do (AM fix) reaches the hardwares limit, your AM RX audio will be all but
non-existent (just like Quansheng's firmware).
On the other hand, FM RX audio will/should be fine.

But, they are nice toys for the price, fun to play with.

## User customization

You can customize the firmware by enabling/disabling various compile options, this allows
us to remove certain firmware features in order to make room in the flash for others.
You'll find the options at the top of "Makefile" ('0' = disable, '1' = enable) ..

```
ENABLE_CLANG                  := 0     **experimental, builds with clang instead of gcc (LTO will be disabled if you enable this)
ENABLE_SWD                    := 0       only needed if using CPU's SWD port (debugging/programming)
ENABLE_OVERLAY                := 0       cpu FLASH stuff, not needed
ENABLE_LTO                    := 1     **experimental, reduces size of compiled firmware but might break EEPROM reads (OVERLAY will be disabled if you enable this)

ENABLE_UART                   := 1       without this you can't configure radio via PC !
ENABLE_AIRCOPY                := 0       easier to just enter frequency with butts
ENABLE_FMRADIO                := 1       WBFM VHF broadcast band receiver
ENABLE_NOAA                   := 0       everything NOAA (only of any use in the USA)
ENABLE_VOICE                  := 0       want to hear voices ?
ENABLE_VOX                    := 1
ENABLE_ALARM                  := 0       TX alarms
ENABLE_TX1750                 := 0       side key 1750Hz TX tone (older style repeater access)
ENABLE_PWRON_PASSWORD         := 0       power-on password stuff
ENABLE_DTMF_CALLING           := 1       DTMF calling fuctionality, sending calls, receiving calls, group calls, contacts list etc.
ENABLE_FLASHLIGHT             := 1       enable top flashlight LED (on, blink, SOS)

ENABLE_BIG_FREQ               := 1       big font frequencies (like original QS firmware)
ENABLE_SMALL_BOLD             := 1       bold channel name/no. (when name + freq channel display mode)
ENABLE_KEEP_MEM_NAME          := 1       maintain channel name when (re)saving memory channel
ENABLE_WIDE_RX                := 1       full 18MHz to 1300MHz RX (though front-end/PA not designed for full range)
ENABLE_TX_WHEN_AM             := 0       allow TX (always FM) when RX is set to AM
ENABLE_F_CAL_MENU             := 0       enable the radios hidden frequency calibration menu
ENABLE_CTCSS_TAIL_PHASE_SHIFT := 0       standard CTCSS tail phase shift rather than QS's own 55Hz tone method
ENABLE_BOOT_BEEPS             := 0       gives user audio feedback on volume knob position at boot-up
ENABLE_SHOW_CHARGE_LEVEL      := 1       show the charge level when the radio is on charge
ENABLE_REVERSE_BAT_SYMBOL     := 0       mirror the battery symbol on the status bar (+ pole on the right)
ENABLE_NO_CODE_SCAN_TIMEOUT   := 1       disable 32-sec CTCSS/DCS scan timeout (press exit butt instead of time-out to end scan)
ENABLE_AM_FIX                 := 1       dynamically adjust the front end gains when in AM mode to help prevent AM demodulator saturation, ignore the on-screen RSSI level (for now)
ENABLE_AM_FIX_SHOW_DATA       := 0       show debug data for the AM fix
ENABLE_SQUELCH_MORE_SENSITIVE := 1       make squelch levels a little bit more sensitive - I plan to let user adjust the values themselves
ENABLE_FASTER_CHANNEL_SCAN    := 1       increases the channel scan speed, but the squelch is also made more twitchy
ENABLE_RSSI_BAR               := 1       enable a dBm/Sn RSSI bar graph level in place of the little antenna symbols
ENABLE_AUDIO_BAR              := 1       experimental, display an audio bar level when TX'ing
ENABLE_COPY_CHAN_TO_VFO       := 1       copy current channel into the other VFO. Long press `1 BAND` when in channel mode
ENABLE_SPECTRUM               := 1       fagci spectrum analyzer, activated with `F` + `5 NOAA`
ENABLE_REDUCE_LOW_MID_TX_POWER:= 0       makes medium and low power settings even lower
ENABLE_BYP_RAW_DEMODULATORS   := 0       additional BYP (bypass?) and RAW demodulation options, proved not to be very useful, but it is there if you want to experiment
ENABLE_BLMIN_TMP_OFF          := 0       additional function for configurable buttons that toggles `BLMin` on and off wihout saving it to the EEPROM
ENABLE_SCAN_RANGES            := 1       scan range mode for frequency scanning, see wiki for instructions (radio operation -> frequency scanning)
```


## Compiler

arm-none-eabi GCC version 10.3.1 is recommended, which is the current version on Ubuntu 22.04.03 LTS.
Other versions may generate a flash file that is too big.
You can get an appropriate version from: https://developer.arm.com/downloads/-/gnu-rm

clang may be used but isn't fully supported. Resulting binaries may also be bigger.
You can get it from: https://releases.llvm.org/download.html

## Building

### Github Codespace build method

This is the least demanding option as you don't have to install enything on your computer. All you need is Github account.

1. Go to https://github.com/egzumer/uv-k5-firmware-custom
1. Click green `Code` button
1. Change tab from `Local` to `Codespace`
1. Click green `Create codespace on main` button

<img src="images/codespace1.png" width=700 />

5. Open `Makefile`
1. Edit build options, save `Makefile` changes
1. Run `./compile-with-docker.sh` in terminal window
1. Open folder `compiled-firmware`
1. Right click `firmware.packed.bin`
1. Click `Download`, now you should have a firmware on your computer that you can proceed to flash on your radio. You can use [online flasher](https://egzumer.github.io/uvtools)

<img src="images/codespace2.png" width=700 />

### Docker build method

If you have docker installed you can use [compile-with-docker.bat](./compile-with-docker.bat) (Windows) or [compile-with-docker.sh](./compile-with-docker.sh) (Linux/Mac), the output files are created in `compiled-firmware` folder. This method gives significantly smaller binaries, I've seen differences up to 1kb, so it can fit more functionalities this way. The challenge can be (or not) installing docker itself.

### Windows environment build method

1. Open windows command line and run:
    ```
    winget install -e -h git.git Python.Python.3.8 GnuWin32.Make
    winget install -e -h Arm.GnuArmEmbeddedToolchain -v "10 2021.10"
    ```
2. Close command line, open a new one and run:
    ```
    pip install --user --upgrade pip
    pip install crcmod
    mkdir c:\projects & cd /D c:/projects
    git clone https://github.com/egzumer/uv-k5-firmware-custom.git
    ```
3. From now on you can build the firmware by going to `c:\projects\uv-k5-firmware-custom` and running `win_make.bat` or by running a command line:
    ```
    cd /D c:\projects\uv-k5-firmware-custom
    win_make.bat
    ```
4. To reset the repository and pull new changes run (!!! it will delete all your changes !!!):
    ```
    cd /D c:\projects\uv-k5-firmware-custom
    git reset --hard & git clean -fd & git pull
    ```

I've left some notes in the win_make.bat file to maybe help with stuff.

## Credits

Many thanks to various people on Telegram for putting up with me during this effort and helping:

* [OneOfEleven](https://github.com/OneOfEleven)
* [DualTachyon](https://github.com/DualTachyon)
* [Mikhail](https://github.com/fagci)
* [Andrej](https://github.com/Tunas1337)
* [Manuel](https://github.com/manujedi)
* @wagner
* @Lohtse Shar
* [@Matoz](https://github.com/spm81)
* @Davide
* @Ismo OH2FTG
* [OneOfEleven](https://github.com/OneOfEleven)
* @d1ced95
* and others I forget

## Other sources of information

[ludwich66 - Quansheng UV-K5 Wiki](https://github.com/ludwich66/Quansheng_UV-K5_Wiki/wiki)<br>
[amnemonic - tools and sources of information](https://github.com/amnemonic/Quansheng_UV-K5_Firmware)

## License

Copyright 2023 Dual Tachyon
https://github.com/DualTachyon

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

## Example changes/updates

<p float="left">
  <img src="/images/image1.png" width=300 />
  <img src="/images/image2.png" width=300 />
  <img src="/images/image3.png" width=300 />
</p>

Video showing the AM fix working ..

<video src="/images/AM_fix.mp4"></video>

<video src="https://github.com/OneOfEleven/uv-k5-firmware-custom/assets/51590168/2a3a9cdc-97da-4966-bf0d-1ce6ad09779c"></video>
