# randomXKCD
Download and display a random XKCD comic in fullscreen with feh. If no internet connection is available, display a previously downloaded one.

## Why?
I write this script to work in conjunction with xautolock like this:

`xautolock -time 10 -notify 60 -notifier randomXKCD -locker 'i3lock -c 000000'`

This has to purpose. The obvious one is to display the comic as a warning before locking the computer. The second is to get a little chuckle when unlocking it. Effectively, feh keep displaying the image behind the lock so it is the first thing to appear when unlocking.

This behavious can easly be changed by killing feh after lock. e.g:

`xautolock -time 10 -notify 60 -notifier randomXKCD -locker 'i3lock -c 000000; pkill feh'`
