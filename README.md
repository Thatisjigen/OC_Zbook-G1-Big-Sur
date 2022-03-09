# ZBook G1 OpenCore EFI

That OC folder is based on OC 0.7.9.

It needs adjustment, as secure boot model is disabled, (otherwise you can't install the OS)

Scanpolicy need adjustment to boot the bootable usb as I'm using OpenCore as a MacOS only bootloader with reefind as a main bootloader (that way ACPI patches are working only on MacOS)

It supports Big Sur only. (Monterey would disable the dGPU).

You need to flash the proper VBIOS for nVidia branch.

For Monterey change SMBIOS and make sure bluetooth is injected (OpenintelBluetooth explain it all).


# Status
**Working:**
- Cpu.
- GPU (iGPU+dGPU).
- - dGPU: in my case NVidia Quadro K2100M with 2GB of dedicated RAM.
- - iGPU: Intel 4600 (with metal disabled to use only the dGPU for rendering). 
- Bluetooth.
- Wifi. (I assume we all use same centrino card, the kext is built from source removing all unused firmware, if it's not working for you just grab the original Airportitwlan kext from Openintelwireless).
- USB (Mapped to avoid using any quirks.
- Battery extimate.
- Realtek Card reader.
- Fan control.
- Webcam.
- Touchpad(NOTE: needs Voodoo Kext which is missing cause my touchpad is dead).
- Brightness control (scaled to use smooth transition and don't make the display black on min value).
- Display resolution control (patched EDID to use full UEFI with CSM disabled).
- Audio (NOTE: layout id is set for best compatibility with audio jack, tho if you don't use it I'd suggest to use the layout id N° 13 cause it gives mic a louder volume.

**Not working:**
- On nVidia the DRM are broken, use Chrome.

--------
# Credits
- @Rehabman for his guide for clover.
- @whenmusicattacks for dGpu  vbios hints.
- @bangmaple cause some mapping is done by him, tho as you can see our EFIs are a lot different and I'm trying to use only minimal kexts and a smaller patchset.
- @chris1111 for his theme, tools and what else he's done for the community.
- All the OC team, OpenintelWireless team, and the OC community.
 
