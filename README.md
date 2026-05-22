# Hackintosh ASUS H110M-K i5-6500 RX580

OpenCore EFI for macOS Ventura on ASUS H110M-K, Intel Core i5-6500, and AMD Radeon RX 580.

## Hardware

| Component | Model |
| --- | --- |
| Motherboard | ASUS H110M-K |
| CPU | Intel Core i5-6500 |
| GPU | AMD Radeon RX 580 8GB |
| Audio | Realtek ALC887 |
| Ethernet | Realtek RTL8111H |
| Storage | SATA SSD/HDD |

## Status

This EFI was generated with OpCore-Simplify and is intended as a Ventura recovery/installer EFI for the hardware above.

Current notes:

- SMBIOS: `iMacPro1,1`
- Audio layout: `2`
- USB: `USBToolBox.kext` + `UTBMap.kext`
- GPU: RX 580 via `WhateverGreen.kext`
- Ethernet: `RealtekRTL8111.kext`

## Important

The public `config.plist` uses placeholder SMBIOS values. Before booting, generate your own values and replace:

- `PlatformInfo -> Generic -> SystemSerialNumber`
- `PlatformInfo -> Generic -> MLB`
- `PlatformInfo -> Generic -> SystemUUID`
- `PlatformInfo -> Generic -> ROM`

Do not reuse SMBIOS values from this repository or any other public EFI.

## BIOS Baseline

- Disable Secure Boot
- Disable Fast Boot
- Set SATA mode to AHCI
- Set primary display to PCIe/PEG
- Disable iGPU multi-monitor if using RX 580 as the only display GPU
- CSM disabled is preferred for UEFI boot

## Post-Install Checklist

- Verify all USB ports and rebuild `UTBMap.kext` if needed
- Test audio layouts if layout `2` does not work
- Remove verbose/debug boot args after the system is stable
- Re-enable SIP if no patch requires it disabled
- Copy EFI to the macOS disk's EFI partition after install

## Credits

- [Acidanthera OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [Lilu](https://github.com/acidanthera/Lilu)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
- [AppleALC](https://github.com/acidanthera/AppleALC)
- [USBToolBox](https://github.com/USBToolBox)
- [RealtekRTL8111](https://github.com/Mieze/RTL8111_driver_for_OS_X)
