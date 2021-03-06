# monitormode
This rather short bash script will put a network interface (WNIC) into monitor mode. (and back into managed mode if you like).

## Context
There is (2020) currently a pandemic going on, COVID-19. So while everyone inluding me is in quarantine, I just figured I should use this isolated time to learn new things.
My goal was to learn shell scripting, and to start using Git and GitHub for projects.

This script is made because `sudo airmon-ng start <INTERFACE>` didn't work for my network adapter, to put in into monitor mode. And I wanted to do it myself. It's a plain easy script really..

## How to use?
This script is made on / for (Debian) Kali Linux and makes use of `ip` and `iw`. Usage:
```bash
(sudo) monitormode <INTERFACE> <MODE>
```
`interface`: the interface you want to change (prob. wlan0 or wlan1).
`mode`: the mode you want to use (only monitor or managed are available for this script).

#### Extra adapter info (ALFA AWUS036ACH):
firstly I had to install a realtek driver to use my new adapter: 
```bash
sudo apt install realtek-rtl88xxau-dkms
```
Secondly (deprecated) I had to turn off auto MAC spoofing from NetworkManager, because it could interfere with:
1. Getting wireless internet
2. Manually changing a MAC address

I turned it off by making a file in the /etc/NetworkManager/conf.d directory.
Give the file a name and include the lines: 
```
[device-mac-randomization]
wifi.scan-rand-mac-address=no
```

## ToDo
* I will include some MAC-spoofing for the adapter in the future
