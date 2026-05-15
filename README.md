# **pinkie**

![pinkie](docs/banner.png)

<div align="center">
<p>A portable, wireless, ergonomic split keyboard.</p>
</div>

[![“Buy Me A Coffee”](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/scryagain)

-----

> [!CAUTION]
> **Pre-validation release.** The ordered PCB prototype has not been received yet. Functionality is unconfirmed. Files may change.

-----

## What is **pinkie**?

**pinkie** is an ergonomic split keyboard designed to go wherever you do. The two halves clip into a travel bracket with the keys facing inward, keeping it compact and protected on the move. It runs wirelessly on ZMK firmware with low profile Gateron switches, a reversible PCB that builds both halves from a single board, and a case you can 3D print or CNC mill yourself.

For more information visit [pinkie.gabrielschmitz.de](https://pinkie.gabrielschmitz.de)

-----

## What’s in This Repo

```
/3D            STEP and STL files for the case and travel bracket
/pcbs          gerber files for the PCB
/plates        gerber files for the top plate
/docs          documentation and build resources
README.md      you are here
```

-----

## Bill of Materials

|Part                                    |Quantity       |Notes                                                                                                                      |Link                                                                                                                         |
|----------------------------------------|---------------|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
|**pinkie** PCB (1.6mm)                  |2              |Order from gerber files, same board for both halves                                                                        |[files](/pcbs)                                                                                                               |
|**pinkie** top plate (1.2mm)            |2              |Order from gerber files, same plate for both halves                                                                        |[files](/plates)                                                                                                             |
|Gateron KS-33 switches                  |52             |Low profile                                                                                                                |[link](https://www.gateron.com/products/gateron-ks-33-low-profile-20-strawberry-chocolate-linear-switch-set?VariantsId=11590)|
|Gateron low profile hot swap sockets 2.0|52             |Optional                                                                                                                   |[link](https://www.gateron.com/products/gateron-low-profile-switch-hot-swap-pcb-socket?VariantsId=10234)                     |
|Diodes                                  |52             |1N4148W SOD-123                                                                                                            |[link](https://www.lcsc.com/product-detail/C81598.html)                                                                      |
|Reset button                            |2              |Optional                                                                                                                   |[link](https://www.lcsc.com/product-detail/C2834918.html)                                                                    |
|JST 1.25mm 2P connector                 |2              |Optional                                                                                                                   |[link](https://www.lcsc.com/product-detail/C668614.html)                                                                     |
|M2x10 screws                            |14             |Ultra thin head recommended                                                                                                |[link](https://de.aliexpress.com/item/1005006332971390.html)                                                                 |
|nice!nano v2                            |2              |Or compatible pinout                                                                                                       |                                                                                                                             |
|3.7V lipo battery                       |2              |303450 recommended                                                                                                         |                                                                                                                             |
|3D printed lipo bracket                 |2              |Made for 303450, but super easy to adjust                                                                                  |[files](/3D)                                                                                                                 |
|spacer bracket                          |2              |3D printed or laser cut from 1.2mm EVA foam                                                                                      |[files](/3D)                                                                                                                 |
|3D printed or CNC milled case           |1 left, 1 right|                                                                                                                           |[files](/3D)                                                                                                                 |
|3D printed travel bracket               |1              |Best results with PETG as support interface when printing in PLA and vice versa. Print in place magnet pockets via pausing.|[files](/3D)                                                                                                                 |
|Round magnets 10 x 3mm                  |4              |                                                                                                                           |                                                                                                                             |
|Round magnets 10 x 1mm                  |4              |                                                                                                                           |                                                                                                                             |

-----

## Guide

> [!CAUTION]
> **Pre-validation release.** The guide has not been validated against a physical build yet. Steps may change. Photos will be added.

→ <docs/guide.md>

-----

## Firmware

Available as soon as my PCB order arrives and everything is tested and validated.

-----

## Licensing

- **Hardware** (design files, CAD, gerbers) — [CC-BY-4.0](LICENSE_CC)
- **ZMK config** — [MIT](LICENSE_MIT)