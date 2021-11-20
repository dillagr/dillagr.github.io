## _Why port forward?_
If you want to access a device behind a NAT-ted network, one of the best and simplest ways to do it is to configure a port-forward from your router to the device itself. This aims to outline the procedure on how to get it done with a PLDT VDSL2 router (HG180U).

Your router may have a different interface but the concept(s) involved are going to the similar.

I specifically wanted to enable port-forwarding for my Linxdot Helium Miner, in order to maximize my rewards. I want to avoid the _relayed_ status of my miner.

![helium-hotspot-relayed.png](https://dillagr.github.io/port-forwarding/PLDT-HG180U/helium-hotspot-relayed.png)

## **_Contents_**
1. [Connect to your Router](#connect-to-your-router)
1. [Obtain the IP Address](#obtain-the-ip-address)
1. [Configure Port Forwardning](#configure-port-forwarding)
1. [Verify Port Forwardning](#verify-port-forwarding)



## [1] Connect To Your Router.

Open either Chrome, Edge, or your favorite browser. You will need to open two (2) tabs. On the first tab, this address or URL:

'''
https://192.168.1.1/cgi-bin/enablesuser.cgi?enable=1
'''

And on the second tab, this address:
'''
https://192.168.1.1/fh
'''

Make sure to browse the first tab. And when the browser returns "Enable super user", browse the second tab.

![router-enable-super-user](https://dillagr.github.io/port-forwarding/PLDT-HG180U/router-enable-super-user.png)


Use the following credentials:
username: adminpldt
password: 3UJUh2VemEfUtesEchEuSHA

(reference: https://pinoytechsaga.blogspot.com/2019/09/pldt-default-admin-password-username.html)

![advanced-nat-virtual-servers](https://dillagr.github.io/port-forwarding/PLDT-HG180U/advanced-nat-virtual-servers.png)


## [2] Obtain The IP Address

Get the _leased_ IP Address of your device from **_Status_** -> **_LAN_** -> **_DHCP Server_**. 

This is usually 192.168.1.x. If there are a number of devices listed (e.g. Phones, Laptops or IoT devices), your device should be identifiable based on its hostname. Take note of the device IP Address as this will be used later.


## [3] Configure Port Forwarding

Go to **_Advanced_** -> **_NAT_** -> **_Virtual Servers_**

![advanced-nat-virtual-servers](https://dillagr.github.io/port-forwarding/PLDT-HG180U/advanced-nat-virtual-servers.png)

Use the following inputs, as shown:

'''
User-defined Service Name: Helium-HNT (Any Name)
Enable: (Tick This)
Remote IP Address: (Leave Blank)
Network Mask: (Leave Blank)
Protocol: TCP/UDP
External Port: 44158 - 44158
Internal Port: 44158
Internal IP Address: 192.168.1.22 (leased IP Address)
'''

![hnt-miner-port-forward](https://dillagr.github.io/port-forwarding/PLDT-HG180U/hnt-miner-port-forward.png)


## [4] Verify Port Forwarding

Verify that TCP port 44158 is indeed open. Open another tab on your browser and go to [_https://portchecker.co_](https://portchecker.co)

You should be able to see that port 44158 is open. This help avoid the _relayed_ status on your Helium miner.

![port-checker-44158](https://dillagr.github.io/port-forwarding/PLDT-HG180U/port-checker-44158.png)


If this guide has helped you in any way and you want to show appreciation for the assistance, buy me coffee by sending me some HNT (133wDhn3StHDRnA4k3tTniJMQcsjzptiaUVkVBHtYnCeh41wi6u) or NANO (nano_158p364qazbb7us7nuk7zqios7awmj4t8d1kurhspzmf9piwpzp49bzrc4zp). Much thanks!