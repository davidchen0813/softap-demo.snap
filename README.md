# softap-demo.snap
[Description]
SoftAP APP for Snappy Ubuntu Core devices (ARM).  
The APP combines 3 parts:
 1. hostapd
 2. dnsmasq
 3. A service to start hostapd and dnsmasq
[Prerequisite]
- Device with at least 2 network interfaces, one to be Wireless.  This APP assumes there are 2 interfaces on the device: eth0 and wlan0
- Due to iptables security policy, iptable_filter and ip6table_filter kernel modules need to be loaded for NAT to work. It can be done by "snappy config", please refer to steps below:
  1. $ snappy config ubuntu-core > ./config
  2. adjust ./config to have this:
     config:
       ubuntu-core:
         load-kernel-modules:
           - iptable_filter
           - ip6table_filter
  3. $ sudo snappy config ubuntu-core ./config
Above steps will create a file in /etc/modules-load.d and need only be done once
[Usage]
- Default SSID/PASSWORD: SoftAP-Canonical/warthogs
[Configuration files]
Configure the following files for your own preferences:
- /apps/router-demo.davidchen/current/usr/bin/dnsmasq.conf
- /apps/router-demo.davidchen/current/usr/bin/hostapd.conf
- /apps/router-demo.davidchen/current/usr/bin/softap
