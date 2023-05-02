# Lock on sleep
* Before sleep/suspend:
  * Run `i3lock`
  * Wait to show the lock screen in order to prevent briefly flashing the desktop later (for security)
* After wake/resume, if not unlocked:
  * Turn off display after very short idle time (1 minute)
  * Suspend the system after inactivity (3 minutes)
* After unlocking:
  * Reset DPMS to a longer delay (10 minutes)
  * Disable the short suspend timeout

To run multiple `xautolock` instances, create symlinks:
```
xautolock2 -> xautolock
xautolock3 -> xautolock
...
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
