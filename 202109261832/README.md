# Controlling Cooling and RGB Settings w/ OpenRGB and LiquidCTL

**RGB is controlled by OpenRGB**

Open RGB is supporting the RGB control of all 6 fans on my machine via the
Corsair lighting node. It is also handling the RGB of my RAM.

**Cooling is controlled by LiquidCTL**

The pump cooler and speed of all fans in the case is being controlled by
LiquidCTL. In order to use this software, the python environment where it exists
must first be activated.
```bash
source ~/virtualenvironments/liquidctl/bin/activate
```
The device is recognized as "Corsair Commander Core".
A list of controls for this device can be found [here](https://github.com/liquidctl/liquidctl/blob/main/docs/corsair-commander-core-guide.md).
Currently, the support for it is limited as I can only view the settings; no
changes to the cooling can be made as of Sun 26 Sep 2021 01:44:17 PM CDT

When done changing the settings, make sure to exit the virtual environment:
```bash
deactivate
```

## Tags
#rgb #cooling
