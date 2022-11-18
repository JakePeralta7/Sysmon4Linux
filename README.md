# Sysmon4Linux

## Overview
Just like sysmon (for Windows), this tool gives us visibility to what happens in our host.

The advantages for using Sysmon4Linux are:
- gives us rich events in the same structure as Sysmon4Windows
- unlike auditd, can actually tell us the username
- event filtering is highly customizable

## Installation
### Ubuntu 18.04, 20.04 & 21.04

1. Register Microsoft key and feed
```
wget -q https://packages.microsoft.com/config/ubuntu/$(lsb_release -rs)/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

2. Install SysmonForLinux
```
sudo apt-get update
sudo apt-get install sysmonforlinux
```