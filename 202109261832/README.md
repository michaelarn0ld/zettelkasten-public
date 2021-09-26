# Controlling Cooling and RGB Settings w/ OpenRGB and LiquidCTL

**There are two ways which I am controlling the RGB settings on my machine.**

One is OpenRGB. To access this, just user the super key to find the app and use
the GUI to change the RGB settings. Currently, this is working for the RAM and
Corsair's case lighting node.

For the pump cooler, two fans on the top of the case, and single fan in the rear
of the case, LiquidCTL is used. LiquidCTL is great because it allows for control
over the fan speed, the pump speed, and the RGB configuration. To access this:
```bash
source ~/virtualenvironments/liquidctl/bin/activate
```

The device that it is recognized as is called "Corsair Commander Core".
A list of controls for this device can be found [here](https://github.com/liquidctl/liquidctl/blob/main/docs/corsair-commander-core-guide.md).
Currently, the support for it is limited I can only view the settings; no
changes to the RGB here can be made as of Sun 26 Sep 2021 01:44:17 PM CDT

When done changing the settings, make sure to exit the virtual environment:
```bash
deactivate
```

## Tags
#linux
