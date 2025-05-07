# Schmitt-Trigger-PCB

Problem: The RFSoC boards like ZCU216 & ZCU111 cannot drive 50 Ohm device on their pmod outputs due to their current limitations. The standard LVCMOS I/O banks can often handle 2-12 mA of current, but to drive a 50-Ohm load, about 66 mA is required.

Solution: The use of a buffer, particularly the dual Schmitt-Trigger buffer (SN74LVC2G17 from TI), allows a tolerance of 24 mA of current at 3.3 V, which enables it to drive the 50-Ohm load.
*Note: RF devices are typically 50-Ohm, but if using components with resistance less than 50 Ohms, Schmitt-Trigger buffer might be insufficient. In this case, make use of a level shifter or an Op-Amp.
Our group tried using an Op-Amp, but most of them required the use of an external power supply, so we continued with level converters or buffers.

Result: The Schmitt-Trigger buffer-mounted PCB was able to drive the RF switch (50 Ohms) but was not able to extend the qubit lifetime as with our intentions.
However, it is highly recommended for RFSoC users to use this kind of device on the pmod outputs of their boards.

# Design

# Soldering
