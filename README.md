# monitormode
Just a script that puts your network adapter in monitor mode. (and back into managed mode). Including some MAC spoofing for safety.

## Disclaimer
My goal was to learn bash scripting, start using Git and GitHub, and I had free time because of the Covid-19 crisis. 
This script was made because `sudo airmon-ng start <INTERFACE>` didn't work for my adapter. I am not responsible for any damage.

## Usage
This script is made for (Debian) Kali Linux and makes use of `airmon-ng` and `macchanger`.

Usage: `(sudo) monitormode <interface> <mode>`

interface: the interface you want to change (prob. wlan0 or wlan1).

mode: the mode you want to use (monitor or managed).

#### Pre:
I had to turn off auto MAC spoofing from NetworkManager, because it could interfere with:
1) Manually changing a MAC address
2) Getting wireless internet

If you have the same problems, it might be handy to try this solution: `sudo nano /etc/NetworkManager/NetworkManager.conf`

Add lines to turn off auto MAC spoofing:

`[device]`

`wifi.scan-rand-mac-address=no`

