# OpenWrt for RPi 4
[![build](https://github.com/damianperera/openwrt-rpi/actions/workflows/build.yml/badge.svg)](https://github.com/damianperera/openwrt-rpi/actions/workflows/build.yml) [![GitHub stars](https://img.shields.io/github/stars/damianperera/openwrt-rpi)](https://github.com/damianperera/openwrt-rpi/stargazers) [![GitHub issues](https://img.shields.io/github/issues/damianperera/openwrt-rpi)](https://github.com/damianperera/openwrt-rpi/issues) [![GitHub license](https://img.shields.io/github/license/damianperera/openwrt-rpi)](https://github.com/damianperera/openwrt-rpi/blob/main/LICENSE) [![Twitter](https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fgithub.com%2Fdamianperera%2Fopenwrt-rpi)](https://twitter.com/intent/tweet?url=https%3A%2F%2Fgithub.com%2Fdamianperera%2Fopenwrt-rpi)

Based off the works of [wulfy23/rpi4](https://github.com/wulfy23/rpi4) and includes the following enhancements:
- Configures a DHCP client so that OpenWrt can obtain an IP address from the WAN network using the onboard Ethernet port
- Configures Google DNS servers so that domain names can be resolved <sup>[1](#recommendations)</sup>
- Configures a 5 GHz WiFi access-point on an isolated LAN network using the onboard WiFi <sup>[2](#recommendations)</sup>
- Allows access to the LuCi web interface from both the LAN and WAN networks <sup>[3](#recommendations)</sup>
- Allows SSH access from both the LAN and WAN networks <sup>[3](#recommendations)</sup>

The above enhancements are intended to provide plug-and-play (PnP) support for the RPi 4, so that you can simply flash the image and get started immediately.

## What is OpenWrt?
> With OpenWrt, users/developers can use their router to run a BitTorrent client, enable VPN, create a guest Wi-Fi network, analyze network traffic, do traffic-shaping or apply QoS rules on packets. The router can also run servers: SSH (and do SSH tunneling), IRC server, HTTP server, FTP server, etc. Mesh networking, port knocking, firewalling, wireless bridging, file sharing and real-time monitoring are some other useful features. When configured as a public hotspot, OpenWrt provides a number of functions to manage the hotspot.
> 
> OpenWrt can also connect to printers, webcams, modems and soundcards. In general, an OpenWrt device can work with any hardware that has Linux support.
> 
> ~ _[Devopedia](https://devopedia.org/openwrt)_

## Requirements
- RPi 4 Model B
- A fast SD card (ideally larger than 2 GB)

## Installation
1. Download the RPi Imager ([macOS](https://downloads.raspberrypi.org/imager/imager_latest.dmg), [Windows](https://downloads.raspberrypi.org/imager/imager_latest.exe), [Ubuntu](https://downloads.raspberrypi.org/imager/imager_latest_amd64.deb))
2. Download the [latest release](https://github.com/damianperera/openwrt-rpi/releases/latest) from this repository
3. Flash the `openwrt.img.gz` file using the RPi Imager onto your SD card

    ![ezgif com-gif-maker](https://user-images.githubusercontent.com/15967502/121747825-456ed380-cb08-11eb-9fad-4398a87d989d.gif)
  
4. Connect your RPi's onboard Ethernet port to your main network router's LAN port and boot up the RPi
5. Wait for the initial setup to complete (5-7 mins)
6. Obtain the IP address of the RPi using your main network (WAN) router and use it to connect to the LuCi Web Interface over your preferred browser. You can also connect to LuCi via the WiFi access point created by OpenWrt by heading over to `192.168.1.1`

## Default Credentials <sup>[2](#recommendations)</sup>
- **LuCi Web Interface:**
  - Username: `root`
  - Password: `root`
- **WiFi Access Point:** 
  - SSID: `OpenWRT WiFi`
  - PassKey: `changeThisPassKey`

## Release Schedule
Automated builds have been scheduled for once a week. Urgent hotfixes will be manually triggered.

---

### Notes
- For more information on the default features included in this build plus usage instructions, please refer the [wulfy23/rpi4](https://github.com/wulfy23/rpi4) repository.
- In the above context WAN refers to your home/office network, and LAN refers to the network created by OpenWrt.

### Recommendations
<sup>1</sup> Change to a more secure DNS provider after installation<br>
<sup>2</sup> Change the default credentials after installation<br>
<sup>3</sup> Restrict LuCi and SSH access to the LAN interface after completing configuration<br>
