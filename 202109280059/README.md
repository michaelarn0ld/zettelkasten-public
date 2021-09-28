# Using the Sony A6300 as a Webcam

Digital cameras can be easily used as a webcam on many Linux distributions. 
Before attempting this, check [here](http://gphoto.org/proj/libgphoto2/support.php)
to make sure the that gPhoto2 supports your digital camera.

There are 3 dependencies for using a digital camera as a webcam on Linux:
* gPhoto2
* v4l2loopback
* ffmpeg
To install these to your system, run:
```bash
sudo apt install gphoto2 v4l2loopback-utils ffmpeg
```

Now, load the v4l2loopback module to your kernel manually by running:
```bash
sudo modprobe v4l2loopback exclusive_caps=1 max_buffers=2
```

Keep in mind that rebooting the system will require rebooting the kernel module.
If you plan on using a digital camera as a webcam on a regular basis, it may be
worth it to ensure the module is loaded on boot by changing the modules config
file:
```bash
$ sudo vim /etc/modules 

# /etc/modules: kernel modules to load at boot time.
#
# This file contains the names of kernel modules that should be loaded
# at boot time, one per line. Lines beginning with "#" are ignored.

v4l2-webcam
```

Create an alias for **v4l2-webcam**:
```bash
$ sudo vim /etc/modprobe.d/v4l2-webcam.conf

alias v4l2-webcam v4l2loopback
options v4l2loopback exclusive_caps=1 max_buffers=2
```

Awesome! Now the module will always be loaded when you reboot your system.
We can start using the actual software now. For convenience, there is a bash
script in ```bash ~/scripts/webcam```. If you are interested in the underlying
usage of the script be sure to check that out. Otherwise, just know that to
start the webcam:
```bash
webcam start
```
Which is an alias for:
```bash
gphoto2 --stdout --capture-movie | ffmpeg -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video0
```
Be sure to replace ```bash /dev/video0``` with whatever the device is output
from ```bash v4l2-ctl --list-devices```

Congrats, you're off to the races and can now stream video from a digital
camera; no capture card required.

## Tags
#linux #bash #webcam #streaming
