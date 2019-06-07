---
layout: post
title: OpenWRT Studying Records
published: true
---

## Current Goals:
1. Install shadowsocks-libev, ChinaDNS to my openWRT router and test its connectivity
2. Set openWRT router as secondary router in my local network，use openwrt as gateway in local network
3. Plug-in available for different types of local networks
4. Can be accessed from outside network (OpenVPN)

## Device Configuration:
-OpenWRT router: a used netgear wndr4300 bought from ebay. Looks good

-Arris router: home main router from RCN (ip address: 192.168.0.1)

-Additional router: netgear R6120

## OpenWRT installation:
netgear wndr4300 has official firmware support, just follow the instruction on [OpenWRT](https://openwrt.org/toh/netgear/wndr4300):
- Connect your computer to the router with an ethernet cable and browse to http://192.168.1.1/ (default credentials are admin password)
- In Netgear web interface go to: Advanced > Administration > Firmware Upgrade 
- Upload the Openwrt firmware: openwrt-18.06.2-ar71xx-nand-wndr4300-ubi-factory.img
- Proceed with the firmware installation and wait some minutes until it finish.

After the installation finished, restart the router and browse to http://192.168.1.1/ (default username: root, no password) and you will find luci already installed

### Issues and solutions in the installation:
1. Reset router after DHCP disabled
I would like to set the openWRT router to be an AP router: 
  - changed the LAN ip address of openWRT router to 192.168.0.20
  - disable the DHCP in openWRT
  - connected the openWRT router to main router with a cable
However, I can never log into the openWRT router anymore

#### Solution: 
Press and hold the "reset button" on the router for 10 seconds, all setting would be reset. And then log in at http://192.168.1.1/






