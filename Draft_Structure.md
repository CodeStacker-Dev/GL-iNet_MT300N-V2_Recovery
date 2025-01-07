# Draft Structure

GL-iNet_MT300N-V2_Recovery/
│
├── README.md ✔️
├── LICENSE ✔️
├── firmware/ - All firmware-related files ✔️
│    ├── original_firmware.bin - Factory firmware ❌
│    └── firmware_information.txt - Information on the factory firmware ❌
│
├── uboot/ - Bootloader files ✔️
│    └── original_uboot.bin ❌
│
├── Documentation/ - Documentation ✔️
|  └──UBoot/
|   ├── Web Based Uboot Recovery.md ✔️
|   ├── Uboot TFTP Recovery Windows.md ✔️
|   └── Uboot TFTP Recovery Linux.md ✔️
│
└── changelogs/ - Version logs and updates ✔️
 ├── firmware_changelog.md ❌
 └── uboot_changelog.md ❌
