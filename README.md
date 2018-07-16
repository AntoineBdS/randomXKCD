# randomXKCD
Download a random xkcd comic and display it with feh or use it as a lockscreen with i3lock. If no internet connection is available, use a previously downloaded image.dd

## Dependencies
- feh
- i3lock

## Usage
`randomXKCD <disp|lock> [last]`

- disp: display a comic
- locl: lock the screen and use a comic as lockscreen
- last: use the last image used

### Examples
This script is intended to be used in conjunction with xautolock in the following ways:

#### Notify
`xautolock -time 10 -notify 60 -notifier 'randomXKCD disp' -locker 'i3lock -c 000000'`

Notify before lock by displaying an xkcd image. The image will still be displayed upon unlocking. To avoid that, you can terminate feh upon locking using the PID of feh saved in the tmp directory:

`xautolock -time 10 -notify 60 -notifier 'randomXKCD disp' -locker 'i3lock -c 000000; kill -SIGTERM $(cat "/tmp/randomXKCD")'`

#### Lock
`xautolock -time 10 -locker 'randomXKCD lock'`

Lock the screen and display a random xkcd.

#### Notify and lock
`xautolock -time 10 -notify 60 -notifier 'randomXKCD disp' -locker  -locker 'randomXKCD lock last'`

Notify by displaying an image and lock reusing the same image.

## Options
Some options are available in the script:

- downloadDir
- tmpDir
- zoomLevel (in percent)
- bgColor (back ground colour given in 3-byte format: rrggbb, same as i3lock -c option)
- resolution (autodetected by default with xrandr)
