# GRAM Slim

# Brook Version

This repo contains within the folder Gram FGC -> v1.brook, an edited version based on the v1.2 version that uses a brook P5-mini board. It's also edited specifically for a layout I find more comfortable, with the thumb button on the right hand outwards, instead of tucked under.

The PCB was made from scratch with heavy inspiration from the V1.2 PCB by [Quark](https://twitter.com/quark_works) as well as the (Flatbox)[https://github.com/jfedor2/flatbox], which includes an example of a Brook mini PCB & it's footprint in the rev3 version.

This project was entirely for my own personal reasons, wanting the split thumb buttons & the pinky buttons on both sides moved down, as well as easier PS5 support (Hence the brook P5 mini). Don't expect the world from the PCB in here, it was my very first time learning Kicad, and if you want to take inspiration for your own edits, I heavily recommend this [stream](https://www.youtube.com/watch?v=zCp_-3P3b8c) by Quark. Though any keyboard PCB tutorials are a good start.

The gram top panel in the panels folder of V1.brook has also been edited to match the new button layout. The reason for choosing the V1.2 version was simply that it's the one I already owned, and I found it a lot easier to figure out what I was looking at with a dissected example next to me.

# Introduction

**GRAM Slim** is a modular low-profile 21-button controller designed for Smash and FGC games. It has the standard pinout for firmwares like HayBox and Pico-Rectangle, and is also compatible with more fleshed-out FGC firmwares like GP2040-CE. With industrial design from GRAM, and PCB designed in collaboration with Quark.Works, this guide goes over a DIY-friendly approach to building the original GRAM Slim, and future guides/repos may hold remixes and modifications.

**If you would like to support the developer of this project, consider purchasing parts like buttons, PCBs, USB-C to GCC cables, and official GRAM builds at [GRAMCTRL.COM](https://www.gramctrl.com) rather than a fab house.**

![DSC01665](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/9f511a19-d980-44b2-9997-7e5d9f5e9759)

## Included Files

Included in this repo is all the files needed to get started with a simple GRAM Slim build:

- **GRAM Slim Frame .stl files**
- **Fab files for top and bottom panels**
- **Template DXF** for customizing top and bottom panels
- **GRAM 24mm keycap button .stl files**

## Additional Information

If you want more info around GRAM builds, both open source and official builds, please join the [GRAM Digital Controllers Discord](https://discord.gg/6TuHw2r2X4) to ask questions and work with the community! I would love to see people creating new interesting designs, and building upon the initial framework.

## Thanks & Acknowledgements

There are several people who made this project possible, either directly or indirectly.

- [Quark](https://twitter.com/quark_works), who did the PCB design on this and many other GRAM projects.
- [Bjart](https://twitter.com/bjartskular2), who developed the OFOF1 chassis, which was the initial development for a lot of the ideas explored in this build, including using PCB fabs for the panels, and the general idea of stacking two panels on a frame for the enclosure.
- My life and business partner [BRUISES](https://twitter.com/bruisesxo), who has turned GRAM into what it is today, and had incredible patience with me as I toiled away at my computer late into the night designing this thing.

# Ordering & Customization Guide

While most of these files are universal and can be used at any fab house, **JLCPCB** has become the de-facto standard for DIY box manufacturing. This is due to their hyper-affordable pricing and low minimum order quantity.

## Bill of Materials

_NOTE: This ordering guide is for the DIY-friendly versions of the Slim. For Screwless panels, Powder-coated aluminum, and custom die-cut/injection molded parts, we do not have a guide, as these are beyond the reach of traditional DIY makers. These parts are still covered under GPLv3._
Per GRAM Slim, you will need (some files can be made using this repository, but I will link to places to purchase them if you would like to avoid MOQs)

- 1 x [GRAM Slim PCB](https://gramctrl.com/products/gram-slim-pcb)
- 1 x set of [Top/Bottom panels](https://gramctrl.com/products/gram-slim-aluminum-panels)
- 21 x [Kailh Choc V1 switches](https://www.moergo.com/products/kailh-choc-v1-key-switches-red-brown-white-pro-red-20-pack?variant=45328736780561) (Red, Red Pro, and Whites are all great choices)
- 21 x [PG1350 Hotswap Sockets](https://mkultra.click/kailh-hotswap-sockets)
- 21 x [GRAM 24mm Choc Keycap Buttons](https://gramctrl.com/products/gram-24mm-choc-v1-keycap-buttons)
- 1 x GRAM Slim Frame
- 7 x [M5x0.8 8mm Low-Profile Socket Head Screws](https://www.mcmaster.com/92855A507)
- 7 x [M5x0.8 Round-Base Weld Nuts](https://www.mcmaster.com/90563A680)

_Optional_

- USB-C to GCC cable for console/adapter play

## Tools Needed

This guide assumes a level of knowledge on soldering and computer literacy. General tool requirements are:

- Soldering iron
- Solder
- USB-C to USB-A cable
- 3mm hex key/allen wrench
- Pliers
- Patience :)

## The PCB

The PCB Fabrication files should come in the form of a _Gerber ZIP file_ and _bom/cpl files_ (usually in Excel spreadsheet formats).

Drag them into the "Upload Gerbers" box at JLCPCB and this page will pop up:

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/399c1986-c4fd-446e-97d9-e55e6c1433eb)

Here you can change the color of the PCB. Green is the fastest and cheapest from JLC, but their black PCBs look _siiiiiick_. The only setting I recommend you change is to check "**Yes**" on _Confirm Production file_. This allows for any mistakes to be ironed out by their engineers.

Towards the bottom of the page, you want to turn on the switch for **PCB ASSEMBLY**.

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/349919ce-35f1-425e-aabc-416f8ca25363)

Make sure you are assembling the _Bottom Side_ of the PCB, and make sure to set _Confirm Parts Placement_ to "**Yes**". None of the advanced options need to be changed.

Upon confirming your PCB Assembly options, you'll be taken to the Assembly wizard. Clicking next will give you a location to upload the _BOM_ and _CPL_ files (_CPL_ is referred to as _Positions_ in the GRAM Slim files). Once you click through, you'll be brought to you BOM list.

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/36b6bb49-a48a-4550-983b-55a35bed7615)

This will allow you to modify parts if there's any low stock. There's a line at the bottom for CH1-CH21 with some red text. This is for assembling hotswap sockets, which is not recommended for JLC, as you have to preorder them. when you click **next**, continue by clicking _Do not place_.

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/b6534da2-4ae0-4e29-a1a3-f0b06aea3565)

The wizard looks intimidating, but good news! Since you're confirming part placement, the JLC engineers will fix any errors. Just go ahead and continue.

There you have it! Your PCB is ready to order. As of the time of this writing, a set of 5 assembled boards costs $56.07 before shipping.

## The Panels

The process of ordering aluminum panels from JLC is similar to the PCB ordering process, but much simpler. Start by dragging the **GRAM Slim Top** Zip file into the JLC upload window. We want an aluminum PCB, 1.6mm. You can choose either white or black coating (white tends to be glossy, black is matte but a fingerprint magnet).

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/cfec88fb-68bb-479e-8c88-61d2a660c8fc)

Under High-spec Options, make sure to remove order number, or else they'll put an ugly serial number on the panel.

Once you save to cart, you'll see this screen:

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/218c9ba4-145b-4697-92de-b3484fcedc13)

Here you can add the **GRAM Slim Bottom** Zip file, and it will copy all your settings from the Top panel. Save to cart, and you're ready to check out with your PCBs!

_Note: JLCPCB cannot transact PCB and 3D printing orders together, so place this order, then move on to 3D printing._

## The Frame

The frame file is pretty self explanatory. Just go into JLC's 3D printing section, drop the STL file in, and choose your material. I recommend black Resin, but LEDO 6060 is a great, low cost alternative. The only material I recommend against is the textured Nylon options, as the tolerances between the frame and panels are extremely tight, and the texture could interfere with that. make sure the surface finish is set to _sanded_.

![image](https://github.com/GrammyMoney/GRAM-SLIM/assets/126632196/7fee3cdb-1453-4f1a-8c41-a377b9aa191a)

## The Buttons

In the files, there are two versions. A single button for reference, and a 10x .STL file for mass printing at JLC. Each GRAM Slim requires 2.1 prints, so to make the minimum order quantity of 5 PCBs, you will need to order 11 prints of it.

The 10x file is the ideal for JLC, as it minimizes cost. JLC may reach out to you and add some cost (0.30/pc) for small parts. This is normal.

The buttons have been tested in 4 material materials:

- **LEDO 6060** (natural white, most cost-effective option, goes well with matching frame and black aluminum panels)
- **Black Resin** (matte grayish-black, goes well with both black and white panels)
- **PA12-HP Nylon** (Only slightly more expensive for buttons, but gives an amazing textured finish, very premium feel)
- **8001 Transparent Resin** (Really cool, really expensive)

# Build Guide

Building the GRAMv2 is relatively straightforward, but an updated in-depth build guide (including a video!) is currently in the works.
