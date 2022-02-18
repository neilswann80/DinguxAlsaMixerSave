The AlsaMixer command-line tool /usr/sbin/alsactl is missing in ODBeta, so the script by @vloschiavo isn't going to work on the Adam Image.

I grabbed alsactl from the original OD and confirmed it works with ODBeta and I've rewritten the script to use it:
https://github.com/neilswann80/DinguxAlsaMixerSave

S91alsaSettings as before needs to be saved here:
/media/data/local/etc/init.d (via ssh or a linux PC)

When the script runs for the first time it ensures there's a directory called /media/sdcard/ALSA and creates a file named delete2reset within it; this file can be deleted at any time via commander on the device, then upon reboot the AlsaMixer defaults are restored.

I've added the alsactl file needed for this script to run as a release (via the same link above); it needs to be saved in /media/sdcard/ALSA.

NOTE: I did notice a weird quirk with AlsaMixer in that it doesn't seem to close down properly. As you navigate through SimpleMenu on the D-pad after running AlsaMixer, the D-pad presses seem to keep affecting volume changes with AlsaMixer. I would suggest after setting a volume in AlsaMixer, press select to exit, them immediately press start and shutdown the device. You can then power it straight back on and use the device without worry of AlsaMixer settings being interferred with.
