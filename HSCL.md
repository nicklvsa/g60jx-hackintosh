# G60/G51 Hardware/Software Compatibility List #

Much of this was taken from the HCL at wiki.osx86project.org.

|Parts|Device|Working|Notes|
|:----|:-----|:------|:----|
|OSX Version|10.6.4|Yes|  |
|Processor|Intel Core i5-430M|Yes|Requires [Chameleon 2 RC5 rev411](http://g60jx-hackintosh.googlecode.com/files/ChameleonRC5.rev411.pkg.zip) for proper Busratio/C&Pstates. Requires GenerateCStates=Yes and GeneratePStates=Yes in com.apple.Boot.plist.|
|Chipset|Intel HM55 Express|Yes|Requires [MBP 1.3 update](http://redirectingat.com/?id=292X457&xs=1&url=http%3A%2F%2Fsupport.apple.com%2Fkb%2FDL1026&sref=http%3A%2F%2Fwww.insanelymac.com%2Fforum%2Findex.php%3Fshowtopic%3D219591) or [10.6.4 Combo Update](http://support.apple.com/downloads/DL1048/en_US/MacOSXUpdCombo10.6.4.dmg).|
|Bus PCIe|? |? |? |
|SATA|Intel HM55 Express|Yes|Requires [MBP 1.3 update](http://redirectingat.com/?id=292X457&xs=1&url=http%3A%2F%2Fsupport.apple.com%2Fkb%2FDL1026&sref=http%3A%2F%2Fwww.insanelymac.com%2Fforum%2Findex.php%3Fshowtopic%3D219591) or [10.6.4 Combo Update](http://support.apple.com/downloads/DL1048/en_US/MacOSXUpdCombo10.6.4.dmg).|
|PATA|DVD+/-RW|Yes|Native Support.|
|Graphics|Nvidia GeForce GTS 360M|Yes|Requires [MBP 1.3 update](http://redirectingat.com/?id=292X457&xs=1&url=http%3A%2F%2Fsupport.apple.com%2Fkb%2FDL1026&sref=http%3A%2F%2Fwww.insanelymac.com%2Fforum%2Findex.php%3Fshowtopic%3D219591) or [10.6.4 Combo Update](http://support.apple.com/downloads/DL1048/en_US/MacOSXUpdCombo10.6.4.dmg). Benefits include Full Hardware Acceleration 1366x768, (QE), VGA Out, HDMI Out. GraphicsEnabler=Yes needs to be added to com.apple.Boot.plist.|
|SMC|Fake Device|Yes|Requires [FakeSMC.kext.](http://g60jx-hackintosh.googlecode.com/files/fakesmc2.5_release.zip)|
|Audio|Intel HDA Controller / Realtek ALC663 HDA codec|Yes|Requires Slice and Autumn's rewrite of [VoodooHDA.kext](http://g60jx-hackintosh.googlecode.com/files/VoodooHDA.kext_261_Snow.zip) with info.plist hacks to change IOPCIClassMatch to IOPCIMatch with a device ID of 0x3b568086. Microphone works with proper [VoodooHDA Preference Pane Settings](VoodooHDA#VoodooHDA_Preference_Pane_Settings.md).|
|Wireless|Atheros AR9285 Wireless Network Adapter (b/g/n)|Yes|Requires [IO80211Family.kext](http://g60jx-hackintosh.googlecode.com/files/IO80211Family.kext.zip) from update 10.6.5. Doesn't seem to work properly with Wireless N networking. Mixed mode B/G works fine.|
|Ethernet|Atheros AR8131 PCI-E Gigabit Ethernet Controller|Yes|Requires [Attansic/Atheros L1C Ethernet Kext](http://g60jx-hackintosh.googlecode.com/files/build_x64_20100425.zip).|
|USB EHCI & UHCI|Intel HM55 Express|Yes|Native Support.|
|Trackpad|Synaptics PS/2 Port Compatible Trackpad|Yes|Requires [MeklortApplePS2 64bit Kext](http://g60jx-hackintosh.googlecode.com/files/MeklortApplePs2.32.64.zip).|
|Keyboard|Standard PS2 Laptop Keyboard|Yes|FN key functionality can be restored by using Meklort's [AsusHotKeys.kext](http://g60jx-hackintosh.googlecode.com/files/AsusHotkeys.zip). Keyboard backlight hotkeys are not yet implemented, but support is coming soon.|
|Webcam|Chicony CNF71297 (USB 2.0 1.3M UVC WebCam)|Yes|Native Support. Preview mode has a choppy frame rate, but Skype and iChat have smooth playback. Preview mode might only affect Photo Booth and self previews before entering a Video Chat.|
|Battery|Integrated|Yes|Requires [VoodooBattery.kext](http://g60jx-hackintosh.googlecode.com/files/VoodooBattery.kext.zip).|
|Card Reader|Ricoh R5U230 PCIe Memory Stick Host Controller / R5U852? PCIe xD-Picture Card Controller / R5U822 PCIe SD/MMC Host Controller (SDA Standard Compliant SD Host Controller)|No|No known kext can fix this issue. Do NOT try VoodooSDHC, it doesn't work and might get you stuck with a kernel panic on boot.|
|Firewire|Ricoh R5U832 PCIe IEEE1394 Firewire Host Controller|Untested|Appears to be functional based on System Profiler information.|
|Sleep|S3 Hibernate|Yes|Requires this [Extensively Hacked DSDT](http://g60jx-hackintosh.googlecode.com/files/Asus_G51Jx_Bios_108_DSDT_KIZWAN_FIX_FINAL_IRQ_FIXES.aml.zip) from oSXFr33k. This is a work in progress. USB ports don't fully turn off, and lid light blinks as if the system is in S1 standby mode.|