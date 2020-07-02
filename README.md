# monitormode
This script helps you putting a network interface into monitor mode. (and back into managed mode).

## Why
There is currently a pandemic going on (Covid-19).. So while everyone is in quarantine, I just figured to use this isolated time to learn new things.
My goal was to learn bash scripting, and to start using Git and GitHub.

This script was made because `sudo airmon-ng start <INTERFACE>` didn't work for my network adapter. Adapter used: Alfa awus036ach
It's a plain easy script really..

## Usage
This script is made on/for (Debian) Kali Linux and makes use of `ip` and `iw`.

Usage: `(sudo) monitormode <interface> <mode>`

interface: the interface you want to change (prob. wlan0 or wlan1).

mode: the mode you want to use (only monitor or managed are available for this script).

#### Adapter:
firstly I had to install a realtek driver to use the adapter: `sudo apt install realtek-rtl88xxau-dkms`

Secondly I had to turn off auto MAC spoofing from NetworkManager, because it could interfere with:
1) Manually changing a MAC address
2) Getting wireless internet

I turned it off by making a file in the /etc/NetworkManager/conf.d directory.
Give the file a name and include the lines: `[device-mac-randomization]
wifi.scan-rand-mac-address=no`

#### ToDo
I will include some MAC-spoofing for the adapter in the future
