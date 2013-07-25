CameraControl
=============

Bash script to change parameters on X10 style wireless IP cameras

This script is a command line interface to X10 style wireless IP cameras. It is
written in bash and builds heavily (I do mean heavily) on JM's work posted on
blogspot.com
[here](http://a-more-common-hades.blogspot.com/2011/02/foscam-control-script-etc.html)
which I blatantly copied so I could create a command line interface to easily
control multiple X10 wireless cameras.

My use case is that I wanted to be able to quickly activate my cameras to sense
motion, send emails, upload pictures, etc. when I leave my home without having
to log in to each of their web interfaces and toggle various settings every
time. This is quite cumbersome and annoying so I began to look for automatable
ways to do this and stubbled upon JM's bash script.

This script does do some error checking, like checking to make sure the
username/password combination is correct, checking for camera connectivity,
etc. and also logs what it does to a configurable log file. This script could
still use a lot of clean up and customization; I would really like to clean up
the command line argument parsing.

Examples
--------

Activate motion sensing, turn on mail, upload pictures, control image capture
frequency, motion detection correction and sensitivity, while sleeping for 2
seconds between each camera update.

```
camControl alarm on s 2 interval 1 s 2 mdc on s 2 mail on s 2 sense 7
```

Deactivate all motion detection.

```
camControl alarm off
```

Perhaps most importantly, get help.

```
camControl -h
```

Disclaimer
----------

This script has only really been tested for motion/intrusion detection, much of
the camera movement functionality has not been tested. Any feedback is welcome!

Furthermore, I am barly more than a noob when it comes to bash/wget and I do
not claim that this code is well written, efficient, or even safe. Again, any
feedback is welcome.
