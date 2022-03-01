# ZBook G1 OpenCore EFI

That OC folder is based on OC 0.7.8.

It needs adjustment, as secure boot model is disabled (otherwise you can't install nothing)

It supports Big Sur only. (Monterey would disable the dGPU).

Out of the box the dGPU is disabled, that's cause it needs a VBIOS flash. Don't ask me how do it. Once a VBIOS is set just remove "-wegnoegpu" from Boot-args.

For Monterey change SMBIOS and make sure bluetooth is injected (OpenintelBluetooth explain it all).


# Status
**Working:**
- Cpu.
- GPU (iGPU+dGPU).
- - dGPU: in my case NVidia QuadroK2100M with 2GB of dedicated RAM
- - iGPU: Intel 4600 with 4GB of Vram allocated. 
- Bluetooth.
- Wifi. (I assume we all use same centrino card, the kext is built from source removing all unused firmware, if it's not working for you just grab the original Airportitwlan kext from Openintelwireless).
- USB (Mapped to avoid using any quirks.
- Battery extimate .
- Realtek Card reader.
- Fan control.
- Webcam.
- Touchpad(NOTE: needs Voodoo Kext which is missing cause my touchpad is dead)
- Brightness control (scaled to use smooth transition and don't make the display black on min value)
- Display resolution control (display kext is not required, I've made it via Hackintool, you can delete and have a bit faster boot)    
- Audio (NOTE: layout id is set for best compatibility with audio jack, tho if you don't use it I'd suggest to use the layout id N° 13 cause it gives mic a louder volume.

**Not working:**
- As of now I think all is working, except that bluetooth can't be turned off. Tell me if any bug is found.

--------
# Credits
- @Rehabman for his guide for clover
- @whenmusicattacks for dGpu hints
- @bangmaple cause some mapping is done by him, tho as you can see our EFIs are a lot different and I'm trying to use only minimal kexts and a smaller patchset.
- @chris1111 for his theme, tools and what else he's done for the community.
- All the OC team, OpenintelWireless team, and the OC community.
 
