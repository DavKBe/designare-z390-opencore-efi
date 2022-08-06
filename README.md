# Gigabyte z390 Designare Hackintosh 

> ### The king is dead. Long live the king.
> **Thanks to :crown: [baughmann](https://github.com/baughmann)** for passing the torch for me to maintain this repo. I'll try and keep things up to date for everyone and address issues as they come up. I use this computer daily for work and it has been very reliable. I've made quite a few changes to the format and information of this readme so take a read and let me know if anything is unclear.

**Status: Success | Stable**

<img align="right" src="./images/1000-5.png" alt="z390 Designare" width="430">

[![OpenCore](https://img.shields.io/badge/OpenCore-0.8.3-blue.svg)](https://github.com/acidanthera/OpenCorePkg)
[![macOS-stable](https://img.shields.io/badge/macOS-12.5-brightgreen.svg)](https://www.apple.com/macos/monterey)[![macOS-Unstable](https://img.shields.io/badge/macOS-11.6.8-brightgreen.svg)](https://www.apple.com)[![macOS-Unstable](https://img.shields.io/badge/macOS-13.0-yellow.svg)](https://www.apple.com/macos/ventura)

**DISCLAIMER:**

As you embark on your Hackintosh journey you are encouraged to **READ** the entire README and [Dortania](https://dortania.github.io/getting-started/) guides before you start, or check out some [Youtube videos](https://www.youtube.com/c/TechNolli) to get an understanding of the install process. It will save many a message instructing you to read the manual. **I am not an expert**, I haven't forced you to do anything, so put on your big boy pants and take responsibility for any mess you get yourself into.

With that said I'm happy to help when/where I can. When you encounter bug or want to improve this repo, consider opening an issue or pull request. You can also find a wealth of knowledge on [Reddit](https://www.reddit.com/r/hackintosh/), [TonyMacX86](https://www.tonymacx86.com) or [Google](https://www.google.com).

## Introduction

<details> 
<summary><strong>This is not a guide!</strong></summary>


This is not a complete guide. It should only be used as a reference. I provide tips and tricks that I learned on my journey in building a hackintosh. The best way of using this is as a supplement to the OpenCore guide; if you have questions about how to setup your specific hardware, are unclear about what to do, or would like to see the settings I've used.

I understand that some may simply copy the EFI folder to their EFI partition. For clarity the EFI folder needs to go onto the EFI partition.

```EFI
EFI (partition)
	EFI
	├── BOOT
	├── OC
```

It should work and your Gigabyte z390 Designare based hackintosh should boot and work fine. **You will at minimum need to generate SMBIOS values if you want Apple services to work.** Note that all error reporting/logging has been turned off in the config.plist. You will have a difficult time trouble shooting with the setup provided. You can easily turn on the error reporting and logging if you follow the Dortania guide. Best of luck.

> **NOTE** if you simply wish to copy my EFI please do the following:
>
> 1. Properly set your [BIOS settings](https://github.com/seven-of-eleven/designare-z390-opencore-efi/blob/master/BIOS.md)
> 2. [Generate SMBIOS values](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#platforminfo) and add them in the config.plist (MacPro7,1)
> 3. Ensure the value of `showpicker` is `true` in the config.plist file to provide access to the OpenCore menu while booting.
> 4. Prepare your install [USB](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
> 5. Move the entire EFI folder (with your modifications) to the proper partition on your [USB](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting-up-opencore-s-efi-environment) (or [hard drive](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html) once the install is complete).
> 6. [Install](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html#double-checking-your-work) - You need to select <kbd>F12</kbd> to get the boot menu options and **boot from the USB each time the computer restarts** until you've copied the EFI folder onto the hard drive. You may also need to select the correct boot option during install, although this is typically done automatically.

</details>  

<details> 
<summary><strong>This is a guide!</strong></summary>


To install macOS follow the guides provided by [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) :thinking:

</details>  

<details> 
<summary><strong>Shout out and credits</strong></summary>


**Shout out** to [baughmann](https://github.com/baughmann) the OG of this repo. He entrusted it to my care while he's moving on to bigger and better things. All the best to him and many thanks for his contributions.

#### Credit to all these great people whom I don't know but have made my hackintosh dreams come true:

- [EETagent](https://github.com/EETagent) for his repository (I like the layout of his guide and used it to create this one)
- The guys from [Acidanthera](https://github.com/acidanthera) that make this possible
- [Apple](http://apple.com) for macOS and HfsPlus.efi
- [corpnewt](https://github.com/corpnewt) for [USBMap](https://github.com/corpnewt/USBMap) and [CPUFriendDataProvider](https://github.com/corpnewt/CPUFriendFriend)
- [headkaze](https://github.com/headkaze) for [Hackintool](https://github.com/headkaze/Hackintool)
- [Mieze](https://github.com/Mieze) for [IntelMausiEthernet](https://github.com/Mieze/IntelMausiEthernet)
- And every other contributor
- People at [r/hackintosh](https://www.reddit.com/r/hackintosh/) for their advice and help
- Useful tools by [CorpNewt](https://github.com/corpnewt) and [headkaze](https://github.com/headkaze/Hackintool)

</details>

<details>
<summary><strong>Benchmarks (Geekbench 5) 🏎</strong></summary>
<br>



CPU:

- Single-core: [1174](https://browser.geekbench.com/v5/cpu/16318404)
- Multi-core: [7891](https://browser.geekbench.com/v5/cpu/16318404)

Compute (GPU):

- Metals: [79919](https://browser.geekbench.com/v5/compute/5218510)
- OpenCL: [69506](https://browser.geekbench.com/v5/compute/5244655)

</details>

<details>
<summary><strong>Hardware</strong></summary>
<br>


[![UEFI](https://img.shields.io/badge/UEFI-F9i-lightgrey)](https://github.com/baughmann/designaire-z390-intel-i9-9900k-opencore/releases/download/resources/mb_bios_z390-designare_f9i.zip)

#### My system

| Category  | Component                                                    | Note                                                     |
| --------- | ------------------------------------------------------------ | -------------------------------------------------------- |
| CPU       | Intel Core i7-9700k                                          | Other motherboard compatible CPUs shouldn't be an issue  |
| MB        | [Gigabyte Designaire Z390 (rev 1.0)](https://www.gigabyte.com/Motherboard/Z390-DESIGNARE-rev-10#kf) |                                                          |
| GPU       | Saphire Pulse RX 5700 XT                                     | `agdpmod=pikera` needed for 5000 & 6000 series AMD cards |
| SSD       | WD Black 250 GB                                              | Boot drive                                               |
| SSD       | HP EX 950   1TB                                              | Home folder                                              |
| SSD       | WD Blue  2TB                                                 | Video and photo storage                                  |
| SSD       | WB Blue  250GB                                               | Backup boot drive for testing OS update/upgrades         |
| HD        | Seagate Iron Wolf  6TB                                       | Used as internal time machine backup                     |
| Ethernet  | Intel I211 and Intel I219                                    | Dual Gigabit LAN (both working)                          |
| Memory    | 64GB / 3200MHz DDR4                                          |                                                          |
| Wifi & BT |                                                              | Not installed.                                           |
| Case      | [O11 Dynamic](https://lian-li.com/product/pc-o11-dynamic/)   | I have the white version.                                |
| Monitor   | [LG UltraWide 49](https://www.lg.com/us/monitors/lg-49WL95C-W-ultrawide-monitor#) | 49" UltraWide 32:9 Dual QHD (5120 x 1440) IPS Display    |

#### baughmann's system

| Component | Product                           |
| --------- | --------------------------------- |
| CPU       | Intel Core i9 9900K               |
| MB        | Gigabyte Designaire Z390 (rev 10) |
| GPU       | AMD Radeon VII 16 GB              |
| SSD       | Samsung EVO 970 (NVMe - 1TB)      |

#### baughmann's other system

| Component | Product                                 |
| --------- | --------------------------------------- |
| CPU       | Intel Core i7 8700K                     |
| MB        | Gigabyte Designaire Z390 (rev 10) |
| GPU       | AMD Radeon VII 16 GB                    |
| SSD       | Samsung 860 EVO SSD (1TB)               |

#### Other Configurations

- [Without a dedicated GPU](https://github.com/baughmann/Catalina-Gigabyte-Designare-Z390-i9-9900k-EFI/issues/1)
- Other AMD GPU's are _probably mostly_ plug-n-play. Be sure to read the [fantastic Buyer's Guide by Dortania](https://dortania.github.io/GPU-Buyers-Guide/) before you buy!

</details>  

<details>
<summary><strong>Main software</strong></summary>
<br>



| Component      | Version |
| -------------- | ------- |
| macOS Monterey | 12.5    |
| OpenCore       | v0.8.3  |

</details>



<details>
<summary><strong>ACPI Files</strong></summary>
<br>


| Component                |
| ------------------------ |
| SSDT-AWAC.aml            |
| SSDT-EC-USBX-DESKTOP.aml |
| SSDT-PNLF-DRTNIA.aml     |
| SSDT-PMC.aml             |

</details>

<details>
<summary><strong>Kernel extensions</strong></summary>
<br>


| Kext           | Version                                     |
| :------------- | ------------------------------------------- |
| AppleALC       | 1.7.4                                       |
| AppleIGB       | 5.7.2                                       |
| IntelMausi     | 1.0.7                                       |
| Lilu           | 1.6.2                                       |
| RestrictEvents | 1.0.8 - `only needed with SMBIOS MacPro7,1` |
| SMCProcessor   | 1.3.0                                       |
| SMCSuperIO     | 1.3.0                                       |
| USBPorts       | 1.0.0                                       |
| VirtualSMC     | 1.3.0                                       |
| WhateverGreen  | 1.6.1                                       |

</details>



<details>
  <summary><strong>UEFI drivers</strong></summary>
<br>


|       Driver        | Version           |
| :-----------------: | ----------------- |
|     HfsPlus.efi     | 1.0.0             |
|   OpenRuntime.efi   | OpenCorePkg 0.8.3 |
| ResetNvramEntry.efi | 1.0.0             |

</details>



<details>
    <summary><strong>Screenshots</strong></summary>
    <br>
    <p float="left">
        <img src="./images/about_screenshot.png" alt="About this Mac" width="427">
    </p>
    <p float="left">
        <img src="./images/desktop-image.png" alt="Desktop" width="427">
    </p>
    <p float="left">
        <img src="./images/Ventura.jpg" alt="Ventura" width="427">
    </p>
</details> 




## Before installation

<details>  
<summary><strong>UEFI/BIOS settings</strong></summary>
<br>


> Note <kbd>DEL</kbd> key gets you into BIOS Setting during boot.

#### Update (or downgrade) your motherboard's BIOS firmware

Use BIOS version **F9i or F9** (don't use F9j). You can download F9i from this repo's [releases page](https://github.com/seven-of-eleven/designare-z390-opencore-efi/releases/tag/resources) or F9 (the latest version) from [Gigabyte's website](https://www.gigabyte.com/Motherboard/Z390-DESIGNARE-rev-10/support#support-dl-bios).

#### BIOS configuration

Visit the [BIOS configuration](https://github.com/seven-of-eleven/designare-z390-opencore-efi/blob/master/BIOS.md) page to ensure that your BIOS is configured properly.

    Note: If you've recently updated your BIOS firmware, you will need to double-check these as some of them get reset after updating!

</details>  



<details>
<summary><strong>⚠️ HIGHLIGHTED CHANGES FROM PREVIOUS EFI ⚠️</strong></summary>
<br>



The following changes should be noted:

- Audio changed to alcid=11 see `Audio Setup` below
- SMBIOS changed to MacPro7,1
- No Bluetooth or WiFi kexts included - get your fix [here](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#wifi-and-bluetooth)
- AAPL,ig-platform-id - changed from `0300913E` to `0300923E` either should work. I was using the latter and it's working so ¯\\_(ツ)_/¯

</details>



<details>
<summary><strong>Customizing the config.plist</strong></summary>
<br>



Read the official [OpenCore Desktop Guide for Coffee Lake](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html) when making changes to the `config.plist` and the guide's [Gather Files section](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#firmware-drivers) when picking drivers and kexts.

The following fields have been replaced by `[REPLACEME]` (for ease of <kbd>⌘</kbd>+<kbd>F</kbd>):

- `config.plist` > `PlatformInfo`
  - `SystemSerialNumber`
  - `SystemUUID`
  - `MLB`
  - Follow the [OpenCore instructions](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) to generate your own unique identifiers.
- Also replace the ROM value of `11223344 5566` as outlined in the [OpenCore Instructions](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#fixing-rom)
- Choose a `SystemProductName`, either `iMac19,1` or `MacPro7,1` see **Post Install > Generate your own SMBIOS** for details.
- All packages are `RELEASE` and debugging is disabled. If you're having issues, be sure to enable debugging [as described in the OpenCore docs](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#debug), and also grab [the `DEBUG` version of OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases).

</details>



<details>
<summary><strong>Own prev-lang-kbd</strong></summary>
<br>



In the config.plist file you set the default language as outlined in the guide. You can either add it as a string or as a hex data using [ProperTree](https://github.com/corpnewt/ProperTree)

The setting is found in the config.plist under: 

- NVRAM
  - 7C436110-AB2A-4BBB-A880-FE41995C9F82

Format is lang-COUNTRY:keyboard as shown below:

- 🇺🇸 | [0] en_US - U.S --> en-US:0 **OR** ==656e2d55 533a30== in HEX

| Key           | Type   | Value   |
| ------------- | ------ | ------- |
| prev-lang:kbd | String | en-US:0 |

> It is set to English but you can find alternatives here:
>
> [AppleKeyboardLayouts](https://github.com/acidanthera/OpenCorePkg/blob/master/Utilities/AppleKeyboardLayouts/AppleKeyboardLayouts.txt)

</details>

<details>  
<summary><strong>Monterey, BigSur or Ventura?</strong></summary>
<br>



The EFI folder should work for either Monterey, BigSur or Ventura. No idea if it'll work of Catalina. You may need to change AppleIGB kext to get both ethernet ports working in BigSur as the kext required for ethernet has changed a couple times depending on the OS version installed. Also avoid installing Monterey 12.3 it had issues with AMD GPUs that needed DeviceProperties values set for the PCIE device (not included in this EFI). Google is your friend here but it's easiest just not to install 12.3 :grimacing:.

I'm primarily using this EFI with Monterey 12.5 at the moment. I have successfully install Ventura (beta 4) on a secondary drive and everything was working. Let me know if you have issues with BigSur.

</details>  

## Post-Install

<details>  
<summary><strong>Generate your own SMBIOS</strong></summary>
<br>



Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to create your own serial #... based off of your preferred model.

- MacPro7,1 -`What I used`
  - **See below if you want to keep iMac19,1**

**Note:** If you use a different SMBIOS model than the MacPro7,1 that I've used. The provided USB mapping will not work. You will need to edit the **USBPorts.kext** file.  You can right click on the file and select **Show Package Contents**.  From there you can open the Info.plist file in ProperTree and change MacPro7,1 to whatever Model ID you've chosen. This should provide a working USBPorts.kext.

### Keeping SMBIOS iMac19,1

If you've used a previous version from this repo and everything is working for you, **I would recommend you keep the iMac19,1 SMBIOS** so that you don't have to generate new serial numbers etc. In this case you can simply use Propertree to <kbd>delete</kbd> the entire `PlatformInfo` portion of the config.plist file and replace it (copy and paste) with the `PlatformInfo` from your existing config.plist file.

Alternatively you can manually update the `PlatformInfo` by adjusting the following:

| Key                | Type    | Value             |
| ------------------ | ------- | ----------------- |
| CustomMemory       | Boolean | False             |
| MLB                | String  | [REPLACEME] ^*^   |
| ROM                | Data    | 11223344 5566 ^*^ |
| SystemProductName  | String  | iMac19,1          |
| SystemSerialNumber | String  | [REPLACEME] ^*^   |
| SystemUUID         | String  | [REPLACEME] ^*^   |

^*Replace these with your values^

> **NOTE:** If you have everything working with your own USB mapping file. **KEEP IT.** Replace the provided USBPorts.kext file with the one in your existing EFI folder and perform a snapshot in Propertree for good measure.

</details>  



<details>  
<summary><strong>Custom RAM Config</strong></summary>
<br>



> If you're using SMBIOS iMac19,1 you can safely ignore this and just ensure `Kernel>Add> RestrictEvents.kext`> `Enabled` is `False`.

Using the **SMBIOS MacPro7,1** will require either `CustomMemory` to be configured **or** [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents) to be installed. I've enabled the RestrictEvents.kext as default. If you want to create the custom memory values the details can be found in the [guide](https://dortania.github.io/OpenCore-Post-Install/universal/memory.html).

</details>

<details>  
<summary><strong>Audio Setup</strong></summary>
<br>



There are three options available that I'm aware of. You can use alcid 7, 11, or 16. All three are used by different Designare EFIs available online. I'm using alcid 11 because it works for what I need. If you have specific audio requirements and alcid 11 isn't working try the other values. ==Previous EFIs in this repo used alcid=7.==

> NOTE: Alcid values can be added to the 'NVRAM > boot-args' key **or** DeviceProperties. The boot-args value will override the DeviceProperties value if both are used. **You only need one**. This EFI uses the DeviceProperties method.

### Audio output quirks

3.5mm jack will show as Internal Speakers depending on the alcid you've chosen:

| alcid= | Front jack        | Rear jack         |
| ------ | ----------------- | ----------------- |
| 7      | Headphones        | Internal Speakers |
| 11     | Headphones        | Internal Speakers |
| 16     | Internal Speakers | Headphones        |

![audio-options](images/audio-options.png)





alcid decimal to hex value table

| Decimal | Hex value    |
| ------- | ------------ |
| 7       | 07000000     |
| **11**  | **0B000000** |
| 16      | 10000000     |

### Audio setting method used in EFI

DeviceProperties>Add

| Key                        | Type       | Value        |
| -------------------------- | ---------- | ------------ |
| PciRoot(0x0)/Pci(0x1F,0x3) | Dictionary |              |
| layout-id                  | Data       | **0B000000** |

</details>



## Status

<details>  
<summary><strong>What's working ✅</strong></summary>


- [x] GPU hardware acceleration / performance
- [x] iMessage, FaceTime, App Store, iTunes Store. `Generate your own SMBIOS`
- [x] Intel I219-V Ethernet port
- [x] Intel I211 Ethernet port
- [x] Audio jacks - `front and rear 3.5mm audio jacks work with quirks (see Audio Setup for details)`
- [x] Shutdown / Restart / Sleep
- [x] USB 3.0/3/1 - `USB map created.`
- [x] Graphical Boot menu `OpenCanopy (It does work. Not included in OC folder as I generally skip the boot menu.)`
- [x] Thunderbolt 3 - `reported not tested as I have no TB3 devices`
- [x] Sidecar - `reported working, I haven't tested`

</details>  

<details>  
<summary><strong>What's not working ⚠️</strong></summary>


- [ ] All empty . Your hack should work wonderfully.

</details>  

<details>  
<summary><strong>Untested 🧪</strong></summary>



- [ ] Boot chime - `should work I just haven't tried it`
- [ ] FileVault - `should work I just haven't tried it`
- [ ] Windows/Linux from OC boot menu - `I'm not dual booting my system but there's no reason it shouldn't work.`
- [ ] Bluetooth & Wi-Fi - `should work with compatible card`

</details> 

<details>  
<summary><strong>Change log 🪵</strong></summary>



- **6 Aug 2022**
  - Transfer of repo from baughmann to seven-of-eleven
  - Update to **OpenCore 0.8.3**
  - Updated readme format/details
  - Change of SMBIOS from `iMac19,1` to `MacPro7,1` only b/c that's what I'm using
  - Change alcid from 7 to 11
  - Ventura beta 4 is bootable and working
- **11 October 2021**
  - Updated to OpenCore 0.7.4
  - No longer need `slide=0`
  - Removed a bunch of hacky stuff (including USB ports unlimiter)
  - Rebuilt `config.plist` from the ground-up to remove legacy crap that has built up over time
  - Boot times seemed to have improved
  - Tried and failed to use BIOS version F9j
- **30 May 2021:**
  - Confirmed compatability with Big Sur 11.4
- **10 April 2021:**
  - Updated OpenCore to 0.6.9
  - Fixed USB port issue occurring after upgrade to 11.3 by re-disabling `USBInjectAll.kext`, re-enabling `USBPorts.kext` (this mobo's USB map) and setting `Kernel` > `Quirks` > `XhciPortLimit` to `0`
  - Updated all kexts and drivers that needed updating
- **10 April 2020:**
  - Updated OpenCore to 0.6.8
  - Updated all Kexts and Drivers for which there was an update
  - Fixed all non-fatal warnings at startup
  - Ensured compatability with macOS Big Sur 11.2.3 (20D91)
- **15 December 2020:**
  - Updated to OpenCore 0.6.4
  - Updated All Kexts and Drivers for which there was an update
  - Ensured compatability with macOS Big Sur 11.1 (20C69)
- **1 December 2020:**
  - Modified BIOS suggestions to get Sidecar working _(thanks @QueercoreTrash for [#19](https://github.com/seven-of-eleven/designare-z390-opencore-efi/issues/19))_
  - Added a [BIOS configuration page](https://github.com/seven-of-eleven/designare-z390-opencore-efi/blob/master/BIOS.md) with screenshots for user assistance.
- **16 Nov 2020:**
  - Updated to macOS Big Sur from Catalina
  - For some reason, with Big Sur and OC 0.6.3, we no longer need AirportBrcmFix for the Fenvi BT/WiFi Card
  - Changed `slide=1` to `slide=0`
  - Kept `USBPorts.kext` inside the `config.plist`, but disabled it because it seems as though `USBInjectAll.kext` does the trick
- **13 August 2020:**
  - Verified that supplemental update 10.15.6 `19G73` => `19G2021` works without issues.
- **10 August 2020:**
  - Added `SmallTreeIntel82576.kext` for enabling the secondary Ethernet port
- **4 August 2020:**
  - Updated OC to version [0.6.0](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.0)
  - Updated all of [the acidanthera's](https://github.com/acidanthera) drivers and kexts
- **1 August 2020:**
  - Updated OC to version [0.5.9](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.5.9)
  - Updated all kexts and drivers to the latest
  - Removed `ApfsDriverLoader.efi` because it was rolled into OC starting with 0.5.9
- **13 June 2020:**
  - Updated OC, Kernel Extensions, and Drivers to be compatible with latest macOS update `10.15.5` (and supplemental update).
  - Somehow the boot picker remembers my choice now, meaning that emulated NVRAM is somehow working?
  - _IMPORTANT:_ Upgraded from `DEBUG` to `RELEASE`:
    - Changed all drivers and OC files from the `DEBUG` versions to `RELEASE` versions because I seem to have a stable system.
    - Modified `config.plist` to no longer generate logs (log level now `0`).
    - If you're having problems, switch back to `DEBUG` mode yourself by following [this guide](https://dortania.github.io/OpenCore-Desktop-Guide/troubleshooting/debug.html).

</details>
