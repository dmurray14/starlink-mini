# Starlink Mini - General Aviation Info #

## Background ##

Starlink is a constellation of LEO satellites that provide high-speed and low-latency internet around the world. More info [here](https://en.wikipedia.org/wiki/Starlink)

Up until recently, the Starlink terminals were too big and used too much power to be easily used in a general aviation aircraft. Some people, myself included, developed DIY modifications to the Starlink terminal that worked intermittently, but was not at all supported.

With the introduction of the small and lightweight Starlink Mini terminal, it is much easier to use Starlink in a small GA aircraft. The mini terminal accepts a wide DC input range (12-48VDC) and conveniently includes a built-in wifi router.

|Starlink Mini||
|-----|------|
|Weight| 1.10 kg (2.43 lb)|
|Dimensions| 11.75" x 10.2" x 1.45" (298.5mm x 259mm x 38.5mm)|
|Power| 12-48VDC, 60W max|

## Disclaimer ##

The use of the Starlink Mini in an aircraft is not something officially supported by Starlink or SpaceX. The operation described below is within the operational parameters published by Starlink, but use of the Mini terminal in an aircraft is not explicitly permitted. Although it works now, there is no guarantee that they will not change these parameters and/or disable general aviation use in the future. 

Use of the Starlink Mini in an aircraft is at your own risk. Any information provided here is for reference only, and does not represent SpaceX or Starlink. Don't do anything stupid :)

## Plans ##

The Starlink Mini can be used with a number of different Starlink subscription plans. You have a few options:

|Plan|Monthly Cost|Included Data|Overage Data|In-Motion Speed Limit|
|--|--|--|--|--|
|Mini Roam|$50/mo|50GB|$1/GB|~250kts*|
|Mobile Priority|$250/mo|50GB|$2/GB|~250kts*|

<br>*Groundspeed

As of now, the Mini Roam plan is the best option for use in general aviation. Mobile Priority is also an option if you intend to use the Mini terminal on/over the ocean. Mobile Priority traffic also enjoys higher priority on the Starlink network.

Only the above plans will allow high-speed in-motion use. Other plans may appear to work at first, but Starlink will disable your terminal once it is detected in motion for an etended period of time.

## Ordering ##

You can order the Starlink Mini directly from Starlink.

If you choose to do so, you can use my "referral" link here, which gives us both a month of free service: [Order Starlink](https://www.starlink.com/roam?referral=RC-624568-31889-27)

If you do not wish to utilize the referral link: [Order Starlink](https://www.starlink.com/roam)

On this page, click the order now button. For hardware, choose the "Mini" option, and for service, choose "Mini Roam"

#### Important! Order Options ###
Make sure you select the $50/mo Mini Roam option when you order. If you start with the $150/mo option, it will take a full billing cycle to switch back to Mini Roam (and enable in-motion operation).

## Mounts ##

Various DIY mounting solutions have been developed to more easily mount the Starlink Mini terminal in a GA aircraft. The goal of these mounts is to secure the terminal in a safe and *temporary* configuration. I will add more as I find them.

Particularly in aircraft like the Cirrus SR22 with a rear window, I've found suction cups to be an easy and tempoary way of mounting the terminal during flight. The terminal can be easily removed when not in use.

### Suction Cup Mounts

I put together some [simple 3D printed mounts](suction-mounts). These mounts friction-fit to the corners of the Mini terminal and have a slot for a suction cup to be inserted.

Making the mounts:
- Print these mounts using ABS or ASA for high heat tolerance. You may need to scale up the model to acount for shrinkage (0.8% works well for the Bambu X1C). The 3MF is pre-scaled by this amount.
- Use with [these suction cups](https://www.amazon.com/gp/product/B08SMQZ6WC)

Some usage notes:
- Suction cups rely on...suction... to stay attached. GA aircraft are generally unpressurized, so the suction forces decrease as cabin altitude climbs. Make sure to get a good seal, and consider moistening the cup before attaching to the window for best seal.
- On many aircraft including the SR22, windows are adhesive-bonded to the airframe. Some have expressed concern about adding any additional weight to the window. Consider the condition of your window and determine whether you are comfortable suspending the terminal weight from the window. I have personally not had any issues, but you should make your own decision here. 
- I would encourage you to only mount the terminal when actievly using it, and take it down when parked, especially if it's hot out.

## Power Adapters ##

The Mini is observed to use less than 60W at all times (so 100W adapters aren't really even required) and in most cases <30W during operation. 

There are multiple ways of powering the Mini terminal in a 28V aircraft, from most preferred to least:

1. Ship Power - 28V fused & switched
2. Ship Power - USB-C PD Adapter fused & switched
3. Portable Battery Pack (LiFePO4 chemistry highly recommended)

### 1. Ship Power - 28V fused & switched

Because the Mini terminal can accept a wide DC input (12-48V DC), it's possible to power the terminal directly from the aircraft main bus. 28V power is greatly preferred to 12V power, as the Mini has a hard cutoff at 12V. When powered by a 12V bus, longer cables can cause the voltage to the terminal to sag below 12V, which will cause constant resets.

As the Mini draws 60W max, a (60W/28V=) 2.14A draw is expected at 28V. A 3A fuse should be plenty.

Request that your avionics shop install a 28V convenience outlet ("cigarette" outlet) in a location near where you intend to use the Mini terminal. Ensure that this outlet is fused, and request that they install a pilot-accessible switch so that you can turn power to the terminal off and on.

Once you have the outlet installed, you will need a 28V-compatible "Cigarette lighter to barrel jack" adapter to connect to the terminal. Recommended something with at least 18AWG wire gauge (lower number is thicker = better)

The following have been tested: 

- [DC 5.5 x 2.1mm Connector Car Charger Power Supply Cord 10ft - 12v 24v Cigarette Lighter Male Plug with LED Light 16AWG Wire 15A Fuse for Portable DVD Player, Car, Camera](https://www.amazon.com/dp/B098CY7K2K) 

### 2. Ship Power - USB-C PD Adapter fused & switched

<font color="red">Currently, this option is not recommended. The power supplies which have been tested (MidContinent) do not work reliably and cause the terminal to reset. Suggest either option #1 or #3 until resolved. </font> 

The next best option is to have an aviation-grade USB-PD power supply installed. Various avionics companies make USB "PD" (Power Delivery) outlets that are capable of powering the Mini terminal when combined with a USB-C to barrel adapter.

However, the USB PD standard is a bit of a mess and is somewhat confusing. Although all USB-C ports look the same, there are various "profiles" that are supported by the chargers and devices to negotiate the required voltage and current ratings, and not all chargers support them. 

To work with USB-C power, the Mini terminal requires a 20V output profile with at least 3 Amps (this is generally labeled "60W"). Typically, chargers that specifically note the ability to provide 100W power on a single port will work fine. Chargers that are labeled as 60W are less predictable. For example, the 60W outlet in the newer SR22s appears not to support the power required.

The following adapters have been tested and <font color="red"><b>do not work</b></font> with the Mini terminal:

- [MidContinent 6430360-27](https://www.mcico.com/truebluepower/usb-chargers/6430360-27)
- [MidContinent 6430360-37](https://www.mcico.com/truebluepower/usb-chargers/6430360-37)

Once installed, you will need an adapter to "trigger" the charger to supply the correct 20V output, and to physically convert the power to a 5.5x2.1mm barrel jack.

The following adapters have been tested working:

- [2PCS 5.9ft 100W 20V 5A PD Trigger USB Type C Male Input to DC 5.5 x 2.1mm Male Power Cable](https://www.amazon.com/dp/B0BW4KNM68) - adapter and integrated cable
- [100W USB Type C Female to 5.5x2.1mm Male Power Adapter Cable with Dual PD E forChip, Compact Portable for Home, Office, and Travel](https://www.amazon.com/dp/B0CMRBNRNV) - adapter only - requires an additional high-quality USB cable (recommend [Anker](https://www.amazon.com/dp/B08PVPTNZL))

### 3. Portable Battery Pack

Finally, the least intrusive option is to use a portable battery pack. You will obvioiusly need to charge the battery pack before each flight and remember to bring it with you.

I **highly** recommend using only LiFePO4 chemistry battery packs, which are far less volatile in case of a fault or malfunction. Unfortunatley, there aren't really any compact LiFePO4 battery packs available, so you'll end up with something a bit bigger.

When looking for a battery pack, get something that has a 100W USB-C PD output, which will ensure there is plenty of power for the terminal. You will then need to utilize an adapter - choose from any of the above options in the last section.

The mini uses between 20-40W while in operation. Assuming an average of 30W, you can estimate the runtime of the battery by dividing the total energy (Wh) by the power consumption (W). For example, a 256Wh battery pack will last about 8.5 hours.

The following battery packs have been tested working:

|Product|Chemistry|Energy|Approx Runtime|Notes|
|--|--|--|--|--|
|[Anker 521 Portable Power Station](https://www.amazon.com/gp/product/B09FF46FQ9)|LiFePO4|256Wh|8.5h||
|[EcoFlo RIVER 2](https://www.amazon.com/EF-ECOFLOW-Portable-RIVER-Generator/dp/B0B8MXPRDB/)|LiFePO4|256Wh|8.5h||
|[Jackery 100 Plus](https://www.amazon.com/EF-ECOFLOW-Portable-RIVER-Generator/dp/B0B8MXPRDB/)|LiFePO4|99Wh|3.5h|- Supports passthrough charging <br>-Thanks Alek!|
|[Shargeek](https://www.amazon.com/gp/product/B09X9DT3JS/)|<font color="red">LiPoly</font>|73Wh|2.4h||



## Updates ##

I will do my best to keep this information up to date. If you have tested any other configurations that work and would like to share, shoot me an email at starlinkstuff@danmurray.net