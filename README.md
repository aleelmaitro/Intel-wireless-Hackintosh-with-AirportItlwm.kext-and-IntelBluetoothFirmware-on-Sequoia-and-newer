# Intel-wireless-Hackintosh-with-AirportItlwm.kext-and-IntelBluetoothFirmware-on-Sequoia-and-newer
This is the guide to enabling Intel wireless on Hackintosh with Sequoia and more recent versions of macOS.

This is what works on Sequoia, 100% effective.
I've already tested it on many devices.

1- EFI configuration

DeviceProperties

compatible - String - pci14e4,43a0

Kernel:

Add:
IOSkywalkFamily.kext
IO80211FamilyLegacy.kext
AirPortBrcmNIC.kext (Plugin for IO80211FamilyLegacy.kext)
AirportItlwm.kext ("Ventura" version of the latest available release)
BlueToolFixup.kext
IntelBluetoothFirmware.kext
AMFIPass.kext

*The value 24.0.0 must be added to the Min Kernel for all of them.

*The order of the kernel extensions must be exactly as described.

Block
Block IOSkywalkFamily, as mentioned for the OCLP application for Broadcom wireless (exactly the same instruction in the same place)

*You should also add the value 24.0.0 to Min Kernel here.

NVRAM
bluetoothExternalDongleFailed
Type: Data
Value: 00
bluetoothInternalControllerInfo
Type: Data
Value: 00000000 00000000 00000000 0000
csr-active-config - DATA - 03080000

2- Reboot.

3- Apply "Reset NVRAM"

4- Boot the system.

5- Apply OCLP  "OFFICIAL" (NO MOD!!!) (2.4.1 or any new release for Sequoia, or the version required by the operating system)

6- Reboot

Enjoy!!!

Note: This works perfectly on Sequoia. Tahoe may have issues until the official OCLP release is available.
