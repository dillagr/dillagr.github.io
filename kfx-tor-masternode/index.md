# _**HOW-TO: Create a TOR Masternode**_

This applies to any PivX-based blockchain wallets. In particular, the procedure covers the knoxfs (ticker: KFX) cryptocurrency wallet.

**WARNING! This post should not be taken as financial advise. For educational purposes only.**

The reasoning behind this procedure is that running masternodes require a public IP address, either ipv4 or ipv6. The average home user, then cannot run their own without a VPS (or cloud provider) subscription.

But this can be done in your home.. On a raspberry pi, here's how.

<br>&nbsp;

## **_Pre-Requisites_**

One very important assumption considered is that the user is already knowledgeable of creating masternodes. A little advanced knowledge of Linux operating system and administration is required.

Before the tl;dr, this procedure is tested on Ubuntu 20.04 LTS system. It might or might not work on earlier versions.

Make sure you have an SSH client (like PuTTY, or KiTTY) installed and able to login to your server or virtual machine.

<br>&nbsp;

## **_Install TOR_**

First install tor. For Ubuntu, this is done via the apt (or apt-get) command.

```
sudo apt-get update
sudo apt-get -y install tor
```

<br>&nbsp;

## **_Configure TOR_**

Once installed, edit the file /etc/tor/torrc so that it contains the following lines:

```
RunAsDaemon 1

SocksPolicy accept 127.0.0.1
SocksPolicy reject *

SocksPort 9150

Log notice syslog

LongLivedPorts 29929
```

On your terminal, execute:

```
tor --hash-password [replace-this-with-your-password]
```

Get the output hash of the above command and append to /etc/tor/torrc:

```
HashedControlPassword [the-hash-output-above]
Control Port 9051
```

<br>&nbsp;

## **_Validate TOR Configuration_**

Whenever modifications are made to the configuration file /etc/tor/torrc, it is prudent to validate the change.

```
tor /etc/tor/torrc --verify-config
```

The output should be verbose enough to know if things look good.

After installation and configuration, start the tor service

```
sudo systemctl start tor.service
sudo systemctl enable tor.service
```

.. or ..

```
sudo systemctl enable --now tor.service
```

<br>&nbsp;

## **_Test TOR Configuration_**

Next, verify that the tor service runs properly.

```
sudo systemctl status tor.service
```

Then, test if it works.

```
curl https://icanhazip.com
```

Compare the above output with

```
torsocks curl https://icanhazip.com
```

If the outputs are not the same, it means tor service is working and you are ready to configure your masternode.

<br>&nbsp;

## **_Masternode Configuration_**

Finally, modify the masternode configuration file and append the following lines:

```
listen=1
listenonion=1
discover=1
proxy=127.0.0.1:9150
onion=127.0.0.1:29929
torpassword=[replace-with-hash-password-avove]
```

The above configuration is necessary for the controller wallet. But for the masternode, the onion address needs to be known first.

On the same SSH session, execute this command with the wallet stopped.

```
knoxfsd -debug=tor
```

Lookout for the line that looks like this.. Yours would definitely look different, but would contain the _.onion_ string. Any of these lines indicate the _.onion_ address assigned to the host.

```
AdvertiseLocal: advertising address msni3uqjocq5c4x7.onion:29929
ProcessMessages: advertising address msni3uqjocq5c4x7.onion:29929
```

On your knoxfs.conf file, replace the masternodeaddr line with:

```
masternodeaddr=msni3uqjocq5c4x7.onion:29929
```

Do the same for the masternode.conf on the controlling wallet.

That's it. All that is needed is to start the masternode, which you already know how to do.

<br>&nbsp;

## **_Credits_**

This guide was partially due to the contributions of:
[PivX Forums](https://forum.pivx.org/threads/howto-setup-masternode-or-staker-wallet-behind-tor.588/)
[BossTeck](https://github.com/Bossteck/BOSSTECK_TOR_MN_GUIDE-UPDATED)

<br>&nbsp;

## **_DISCLAIMER_**

Again, this post should not be taken as financial advice. I am not affiliated with knoxfs nor part of its development team. Just an avid masternode runner.

If this guide has helped you in any way and want to appreciate my work, buy me coffee (or beer) by sending some crypto.

```
 KFX | K8m5MeNZJhzYgi6ubX87vu1kW19mg7uWGV
NANO | nano_158p364qazbb7us7nuk7zqios7awmj4t8d1kurhspzmf9piwpzp49bzrc4zp
```

Much thanks!

<br>&nbsp;
