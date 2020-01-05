# syncmp3s
Sync my mp3s to my phone, linux to android

Usage:
    syncmp3s ~/Music /media/usb0

that will sync a semi random selection of mp3s from `~/Music/` to your device connected to `/media/usb0/`

Instead of passing in params to customise it I'm setting environment vars, so use it like

    INCLUDE=Indie,Rock EXCLUDE=Live,NSFK WEIGHTING=128 syncmp3s ~/Music/ /media/usb0/

And that will

 * Only include tracks with mp3 genre tags containing "Indie" or "Rock"
 * exclude tracks tagged "Live" or "NSFK"
 * only include tracks rated 128 or higher

The scores generally related to the number of stars you've given your mp3s. iTunes converts 1 star to 64, 2 stars to 128, 5 stars to 255 etc.

This will pick a random number between 0 and 255 and if you track is rated higher than that then it gets transferred, otherwise it gets removed from the remote device. So higher rated tracks have a better chance of making it.

This requires mid3v2 get it by installing [mutagen](https://bitbucket.org/lazka/mutagen)

Initially here [sync android mp3s with linux](http://www.clarkeology.com/m/23386)

*NSFK* is my "not safe for kids" tag... this if for syncing music to play in the car, my boys are too young to rage against the machine just yet.

Fork me!
