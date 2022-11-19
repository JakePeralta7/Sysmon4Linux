# Sysmon4Linux

## Overview
Just like sysmon (for Windows), this tool gives us visibility to what happens in our host.

The advantages for using Sysmon4Linux are:
- gives us rich events in the same structure as Sysmon4Windows
- splunk gives us 
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
sudo /opt/sysinternalsEBPF/libsysinternalsEBPFinstaller
```

3. Configure Sysmon
```
wget https://raw.githubusercontent.com/JakePeralta7/Sysmon4Linux/main/splunk-config.xml
sudo /opt/sysmon/sysmon -i config.xml -accepteula
```

### RHEL 8

1. Register Microsoft key and feed
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

2. Install SysmonForLinux
```
sudo dnf install sysmonforlinux
sudo /opt/sysinternalsEBPF/libsysinternalsEBPFinstaller
```

## Usage
We can see sysmon logs locally using SysmonLogView
```
cat /var/log/syslog | /opt/sysmon/sysmonLogView
```

## Resources
[Sysmon for Linux](https://medium.com/@olafhartong/sysmon-for-linux-57de7ca48575)