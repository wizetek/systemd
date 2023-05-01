# Lock on sleep
* Run i3lock
* Wait to show the lock screen and prevent flashing the desktop later
* Sleep/suspend
* Wake/resume
* Set DPMS to only 1 min
* Set suspend idle timeout to 3 min
* After unlocking:
  * Reset DPMS to longer
  * Disable the short suspend

To run multiple `xautolock` instances, create symlinks:

xautolock2 -> xautolock<br>
xautolock3 -> xautolock<br>
etc.
