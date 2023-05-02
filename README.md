# Lock on sleep
* Run `i3lock` before system sleep
* Wait to show the lock screen in order to prevent briefly flashing the desktop later
* Sleep/suspend
* Wake/resume
* If not unlocked, turn off display after 1 minute of idle time
* If not unlocked, suspend the system after 3 minutes of inactivity
* After unlocking:
  * Reset DPMS to a longer timeout
  * Disable the short suspend timeout

To run multiple `xautolock` instances, create symlinks:
```
xautolock2 -> xautolock
xautolock3 -> xautolock
```
Place the units in `/etc/systemd/system/` and enable both services:
```
$ systemctl enable on-sleep-lock@yourusername.service
$ systemctl enable on-wake-lock@yourusername.service
```
Put the shell script in `/usr/local/bin/` and make it executable:
```
$ chmod +x on-wake-lock
```
