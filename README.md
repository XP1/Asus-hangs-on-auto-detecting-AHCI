# Asus hangs on auto-detecting AHCI during BIOS POST

## Introduction

When Windows is installed with AHCI enabled in an old Asus motherboard BIOS, especially when existing Windows partitions were removed and re-created by the custom partitioner in the Windows installer, the BIOS will freeze or hang on auto-detecting AHCI during POST. This may be because of a [bug in disk geometry detection](https://social.technet.microsoft.com/Forums/windows/en-US/0185fced-0564-412f-8e10-bec37d020c81/windows-7-64bit-rtm-hang-up-at-bios-boot-auto-detecting-ahci#dddc726f-0439-4a00-a9dd-9547b3810f80) or a [safety feature designed to protect data when the SATA mode is changed](https://www.cnet.com/forums/discussions/why-hdd-is-not-working-in-ahci-mode-594898/).

The Windows 7 installer, for example, partitions the drive differently when AHCI is enabled. This mainly creates the partition problem on the drive. When overwriting an existing Windows instllation, the custom partitioner in the Windows installer duplicates the partition problem, and the problem continues to persist. The solution is to wipe the partition data using a third-party tool, install Windows in IDE mode, and then set AHCI mode after Windows has been set up.

In the first step, there are two options. You can delete all partitions using a partition manager, or you can wipe all data by writing zeros the drive, which is the cleaner option.

## Wipe the drive

1. Download Ultimate Boot CD:
    * http://www.ultimatebootcd.com/download.html
2. Boot "Ultimate Boot CD" > HDD > Disk Wiping > Darik's Boot and Nuke.
3. Write zeros to the entire drive.
    1. Enter.
    2. Set method to quick erase.
    3. Disable verification.
    4. Spacebar to select drive.
    5. F10 to start.
    
## Affected motherboards

* Asus P5K-E/WIFI-AP
