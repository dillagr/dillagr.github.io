## _FAQ: Why Buy a Compatible Hotspot?_

**WARNING! Before buying a hotspot or miner, make sure it is compatible with your regional LoRaWAN frequency.**

This is a good question and has something to do with one of the enforced parameters of _Proof of Coverage v11 (POCv11)_.

<br>&nbsp;

## **_Proof Of Coverage v11 (POCv11)_**
One of the many upcoming changes to _proof of coverage_ and the way miners will operate has something to do with the recent changes in the LoRaWAN Regional Parameters. This change will make the blockchain _region-aware_.

To quote the change:
<blockquote>
Prior to PoCv11, the blockchain was unaware of any region-specific LoRaWAN parameters and had very basic support only for US and EU region power settings. With the introduction of PoCv11 the blockchain can look up regional information, EIRP (Effective Isotropic Radiated Power), and channel plans based on H3 indices. The Helium blockchain uses Uber’s H3 hexagonal-based grid system to map geographical coordinates to indexed locations.
</blockquote>
(reference: [POCv11 Explained and Call to Action](https://www.reddit.com/r/HeliumNetwork/comments/pxety8/pocv11_explained_call_to_action/))

It would be prudent to take some time to read the entirety of the contents of the change in the reference above.

<br>&nbsp;

## **_What Are The LoRaWAN Regional Parameter?_**
Before getting **TL;DR**, the frequency table below outlines the regional parameters.

![helium-lorawan-regional-parameters.png](https://dillagr.github.io/why-compatible-miner/AS923-3/helium-lorawan-regional-parameters.png)

The code is taken from the helium miner github page. And it shows the different frequencies that the miners need to operate for each particular region. It also shows why the miner needs to support (or be compatible with) a particular LoRaWAN region to be able to participate in proof of coverage (and thus earn $HNT tokens).

<br>&nbsp;

## **_Which Hotspots are Compatible to The Philippines?_**
The next question is, which miners are compatible to the Philippines? Reading through the LoRaWAN specification, the Philippines is under region **AS923-3**. Which means, only a few of the current approved miners are compatible.

At the time of this writing, they are: [1] SenseCap M1 (US915, automatically switches to AS923-3), [2] RAKWireless, aka MNTD (US915, automatically switches to AS923-3), [3] Linxdot (AS923-3, same model as US915) and the Bobcat300 (AS923-3 model). Note that for the Bobcat300, the AS923 is a specific model. Other models of the Bobcat300 will not auto-switch to the AS923 frequency.

(**WARNING!** There are reports of Bobcat300, shipping the wrong model, so your mileage may vary.)

<br>&nbsp;

## **_Which Hotspot to Buy?_**
Another good question. Since there is currently a shortage of miners and the demand has sky-rocketed. The short and quick answer to this question is: _the miner you can get your hands on in the fastest possible time_.

However, considering the shortage.. Here's the long answer.

The SenseCap M1 and the MNTD versions of the miners are using the Raspberry Pi CM4 system-on-chip hardware. The current availability of this hardware is projected to be second quarter of 2022 (retail). Maybe a quarter early for original equipment manufacturers. This makes target availability for their hardware late first quarter of 2022.

Linxdot has since transitioned to Rockchip RK-3566 from RPI CM4. Bobcat has been producing their miners off of RK-3566 from the get go. These chips are still available in retail, and that makes it generally available to original equipment manufacturer's as well. It is just a matter of how fast they can churn out units from their factories.

My recommendation is to get the Linxdot, as **they ship straight to the Philippines** (and supports the AS923-3 regional frequency).

<br>&nbsp;

## **_Buy a Linxdot Hotspot*

Check this [detailed guide on how to buy the Linxdot Hotspot](https://dillagr.github.io/how-to-buy/), if you have made up your mind.

<br>&nbsp;

## **_REFERENCES_**
[Helium Miner github repository](https://github.com/helium/miner/)
[LoRaWAN Regional Parameters](https://lora-alliance.org/wp-content/uploads/2021/05/RP-2-1.0.3.pdf)
[PLDT Router Port Forwarding](https://dillagr.github.io/port-forwarding/)

<br>&nbsp;

## **_DISCLAIMER_**
I am not working for Linxdot nor have relatives who work for the company (to my knowledge). I have created this guide since I personally bought their product and am currently waiting for them to ship the hotspot to me.

If this guide has helped you in any way and you want to show appreciation for the assistance, buy me beer by sending some crypto. 

```
 HNT | 133wDhn3StHDRnA4k3tTniJMQcsjzptiaUVkVBHtYnCeh41wi6u
NANO | nano_158p364qazbb7us7nuk7zqios7awmj4t8d1kurhspzmf9piwpzp49bzrc4zp
```

Much thanks!

<br>&nbsp;
