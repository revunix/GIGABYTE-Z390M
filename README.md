## Gigabyte Z390M hackintosh w/ OpenCore

![alt text](https://github.com/revunix/GIGABYTE-Z390M/blob/main/images/aboutmac.png?raw=true)


[![buymeacoffee](https://i.imgur.com/iYsbmQO.png)](https://www.buymeacoffee.com/revunix)


## Hardware
Components | Recommended
------------ | -------------
**Motherboard** | GIGABYTE Z390M - BIOS: [F6i](https://download.gigabyte.com/FileList/BIOS/mb_bios_z390m_f6i.zip)
**CPU** | Intel i5 8600 - 3,1 GHz
**WiFi** | [BCM943602CS](https://www.aliexpress.com/item/32798119149.html)
**Graphics Card** | MSI Radeon RX 580 Armor 8GB OC
RAM | 32GB G.Skill Aegis DDR4-3000Mhz
macOS | 11.0.1 (20B29)
OpenCore | v0.6.5 (stable)


## Included items table
Items | Last Version | Comments
------------ | ------------- | -------------
[BIOS](https://www.gigabyte.com/Motherboard/Z390-M-rev-10/support#support-dl-bios) | F6i | Be sure to upgrade F6i
[OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) | 0.6.5 |
[Lilu](https://github.com/acidanthera/Lilu/releases/latest) | 1.5.1 | 
[AppleALC](https://github.com/acidanthera/AppleALC/releases/latest) | 1.5.6 |
[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases/latest) | 1.2.0 |
[WhateverGreen](https://github.com/acidanthera/whatevergreen/releases/latest) | 1.4.6 |
[NVMeFix](https://github.com/acidanthera/NVMeFix/releases/latest) | 1.0.5 | i don't need
[IntelMausi](https://github.com/acidanthera/IntelMausi) | 1.0.5 |
[CPUFriend](https://github.com/acidanthera/CPUFriend) | 1.2.3 | Disable: Kernel > Add > 7 & 8 [or create!](https://github.com/stevezhengshiqi/one-key-cpufriend)
USBPorts.kext | 1.0 | [Create your own USBPorts.kext!](https://github.com/headkaze/Hackintool/releases/latest)

**Important! Important! Important**
**Highly recommended to try the lastest BIOS 'F6i' version. Download [BIOS](https://download.gigabyte.com/FileList/BIOS/mb_bios_z390m_f6i.zip) and flash it for CFG unlocked, SERIAL PORT disabled from BIOS settings.**


## Updates
* 2021-01-05 / Version 1.1 
	- Released with OpenCore 0.6.5
	- Updated kexts

* 2020-12-12 / Version 1.0
	- Released with OpenCore 0.6.4.


## BIOS Settings

Based on F6i version.

#### First setup,

* Save & Exit
	- Load Optimized Defaults, Save & Exit Setup reboot it.

#### Second setup,

* Tweaker
	- Advanced CPU Settings
		- VT-d → **Disabled**
		- Intel(R) Speed Shift Technology → **Enabled**
		- Energy Efficient Turbo  → **Enabled**
		- Intel(R) Turbo Boost Technology → **Enabled**
		- C-States Control
			- CPU Enhanced Halt(C1E) → **Enabled**
			- C3 State Support → **Enabled**
			- C6/C7 State Support → **Enabled**
			- C8 State Support → **Enabled**
			- C10 State Support → **Enabled**
			- Package C State limit → **Auto**
	- Extreme Memory Profile(X.M.P.) → **Profile 1**
	- Advanced Memory Settings
		- Memory Boot Mode → **Enable Fast Boot**
		- Memory Enhancement Settings → **Enhanced Performance**
* Settings
	- Platform Power
		- Platform Power Management → **Disabled**
		- AC Back → **Always On**
		- ErP → **Disabled**
		- Soft-Off by PWR-BTTN → **Delay 4 Sec.**
		- Power Loading → **Enabled**
		- RC6(Render Standby) → **Enabled**
	- IO Ports
		- Initial Display Output → **PCIe 1 Slot**
		- Internal Graphics → **Enabled**
		- DVMT Pre-Allocated → **64M**
		- DVMT Total-Gfx Mem → **MAX** (Need reboot)
		- Aperture Size → **256M**
		- Audio Controller → **Enabled**
    	- Above 4G Decoding → **Enabled**
    	- Super IO Configuration (F6i BIOS only)
    		- Serial Port → **Disabled**
    	- USB Configuration
    		- XHCI Hand-off → **Enabled**
    		- Legacy USB Support → **Enabled**
    		- USB Mass Storage Driver Support → **Enabled**
    		- Port 60/64 Emulation → **Disabled**
    	- Network Stack Configuration
    		- Network Stack → **Disabled**
	- Miscellaneous
		- Intel Platform Trust Technology(PTT) → **Disabled**
		- Software Guard Extensions(SGX) → **Disabled**
* System Info.
	- System Language → **English**
* Boot
	- CFG Lock → **Disabled** (F6i BIOS only)
	- Full Screen LOGO Show → **Disabled**
	- Fast Boot → **Enabled**
		- PS2 Devices Support → **Disabled**
		- Next Boot After AC Power Loss → **Fast Boot**
	- Windows 8/10 Features → **Other OS**
	- CSM Support → **Disable**
	- Secure Boot → **Disable**
