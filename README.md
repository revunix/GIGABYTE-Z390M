## Gigabyte Z390M hackintosh w/ OpenCore

![alt text](https://github.com/revunix/GIGABYTE-Z390M/blob/main/images/aboutmac.png?raw=true)


[![buymeacoffee](https://i.imgur.com/iYsbmQO.png)](https://www.buymeacoffee.com/revunix)


## Hardware
Components | Recommended
------------ | -------------
**Motherboard** | GIGABYTE Z390M - BIOS: [F6j](https://download.gigabyte.com/FileList/BIOS/mb_bios_z390m_f6j.zip)
**CPU** | Intel i5 8600 - 3,1 GHz
**WiFi** | [BCM943602CS](https://www.aliexpress.com/item/32798119149.html)
**Graphics Card** | MSI Radeon RX 580 Armor 8GB OC
RAM | 32GB G.Skill Aegis DDR4-3000Mhz
macOS | 11.2 (20D64)
OpenCore | v0.6.8 (stable)


## Included items table
Items | Last Version | Comments
------------ | ------------- | -------------
[BIOS](https://www.gigabyte.com/Motherboard/Z390-M-rev-10/support#support-dl-bios) | F6j | Be sure to upgrade F6j
[OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) | 0.6.8 |
[Lilu](https://github.com/acidanthera/Lilu/releases/latest) | 1.5.3 | 
[AppleALC](https://github.com/acidanthera/AppleALC/releases/latest) | 1.6.0 |
[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases/latest) | 1.2.3 |
[WhateverGreen](https://github.com/acidanthera/whatevergreen/releases/latest) | 1.5.0 |
[IntelMausi](https://github.com/acidanthera/IntelMausi) | 1.0.5 |
[CPUFriend](https://github.com/acidanthera/CPUFriend) | 1.2.4 | Disable: Kernel > Add > 7 & 8 [or create!](https://github.com/stevezhengshiqi/one-key-cpufriend)
USBPorts.kext | 1.0 | [Create your own USBPorts.kext!](https://github.com/headkaze/Hackintool/releases/latest)

**Important! Important! Important**
**Highly recommended to try the lastest BIOS 'F6i' version. Download [BIOS](https://download.gigabyte.com/FileList/BIOS/mb_bios_z390m_f6i.zip) and flash it for CFG unlocked, SERIAL PORT disabled from BIOS settings.**


## Updates
* 2021-04-18 / Version 1.3 
	- Released with OpenCore 0.6.8
	- Updated kexts

* 2021-02-14 / Version 1.2 
	- Released with OpenCore 0.6.6
	- Updated kexts
	- Replace HfsPlus.efi with the new OpenHfsPlus.efi

* 2021-01-05 / Version 1.1 
	- Released with OpenCore 0.6.5
	- Updated kexts

* 2020-12-12 / Version 1.0
	- Released with OpenCore 0.6.4.

## iGPU | UHD 360 (i5 8600)
<details>
  <summary>DeviceProperties</summary>

**Boot-arg:**  -wegnoegpu igfxonln=1 igfxagdc=0

```
<dict>
	<key>PciRoot(0x0)/Pci(0x2,0x0)</key>
	<dict>
		<key>AAPL,ig-platform-id</key>
		<data>
		BwCbPg==
		</data>
		<key>device-id</key>
		<data>
		mz4AAA==
		</data>
		<key>enable-hdmi20</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-con0-busid</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-con0-enable</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-con0-pipe</key>
		<data>
		EgAAAA==
		</data>
		<key>framebuffer-con1-busid</key>
		<data>
		AgAAAA==
		</data>
		<key>framebuffer-con1-enable</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-con1-type</key>
		<data>
		AAgAAA==
		</data>
		<key>framebuffer-con2-busid</key>
		<data>
		BAAAAA==
		</data>
		<key>framebuffer-con2-enable</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-con2-type</key>
		<data>
		AAgAAA==
		</data>
		<key>framebuffer-patch-enable</key>
		<data>
		AQAAAA==
		</data>
		<key>framebuffer-unifiedmem</key>
		<data>
		AAAAgA==
		</data>
	</dict>
</dict>
```

</details>


## BIOS Settings

Based on F6j version.

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
