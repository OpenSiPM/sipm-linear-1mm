# overview
This repository contains a 16 channel linear array detector designed for hyperspectral fluorescense imaging. Each channel is composed of a single 1x1 mm Hamamatsu S14160 SiPM mounted in a carrier board. These feed into 16 pole zero filters and 16 transimpedance amplifiers adapted from the OpenSiPM single channel design.



# pcb
The PCB is a 4 layer board that can be manufactured inexpensive (few dollars plus shipping) from a number of prototyping services. It could additionally be assembled with at least the passive components on relatively inexpensive, or it can be hand soldered via reflow. Aside from the Hamamatsdu SiPM, the components are stock at Digikey/Mouser.

[Linear array bill of materials](http://htmlpreview.github.io/?https://github.com/OpenSiPM/sipm-linear-1mm/blob/main/sipm-linear-s14160/bom/ibom.html)

# power supply
The linear sipm PCB requires a bipolar power supply capable of powering the 16 OPA847 opamps, which have about 20 mA of quescent current each on top of any output current.  This is supplied by the power-supply-linear-array project, which uses two sets of linear and negative regulators combined with a charge pump to generate the required currents. 

[Power supply bill of materials](http://htmlpreview.github.io/?https://github.com/OpenSiPM/sipm-linear-1mm/blob/main/power-supply-linear-array/kicad/bom/ibom.html)

# bias generator
The bias generator provides the high voltage (~49V) required to bias the SPAD cells in the SiPM. Two versions are provided, a standard one using USB-C and a modified one with a second USB-C connector that allows connecting to an external USB-C power supply.  This can be useful as the total array power is about 3W, and so exceeds the 2.5W supplied by USB2 devices.  By using the second port, the power per port can be kept under 500 mA for hubs and hosts that are not USB3 or USB-C.  

[Power supply bill of materials](http://htmlpreview.github.io/?https://github.com/OpenSiPM/sipm-linear-1mm/blob/main/bias-control-lt8364-linear/bom/ibom.html)
