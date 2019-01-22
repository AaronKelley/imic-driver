The Griffin iMic USB audio input/output device does not work with Windows 10.

I did some testing on older Windows versions and the only 64-bit version that works is Windows XP Professional x64 Edition.  I packaged up the "USB composite device" driver from that version of Windows and made some tweaks so that it can be used on 64-bit Windows 10, side-by-side with Windows 10's "USB composite device" driver.  This could also be potentially used with other USB devices that show up as a "USB composite device" and error on Windows 10 but not Windows XP.

I signed the driver files so that Windows will load the without "test signing mode" or "disable driver signature checking" being enabled.  However, there is no EV certificate, so you will have to make a registry change in order to load the driver.

```
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\CI\Policy]
"UpgradedSystem"=dword:00000000
```

Additional information and possible alternate solutions can be found here:
https://www.geoffchappell.com/notes/security/whqlsettings/index.htm

Note that there are two versions of the Griffin iMic.  I have only tested this with the clear/silver plastic version, not the white one.
