# rpi_level_shifter_v1
Raspberry Pi level shifter for 10 signals (two boards can fit on the same 40 pin header). Two NVT2010PW ICs are available on a single board, to either level shift from 3.3V to 5V or from 3.3V to 1.8V and 1.2V (jumper selectable). The RPi's 5V is used for the 5V level shift and two on-board LDO regulators are available for shifting levels down to 1.8V or 1.2V. Other voltages can be used, but it is recommended that they not be between 2.6V and 4.3V.  

This board is designed to not fit over-top the RPi board, but rather over the side.

![picture](https://github.com/charkster/rpi_level_shifter_v1/blob/main/rpi_level_shifter_v1_pcb.png)

Each board needs to have the top-left pin of J1 connected to the 3.3V RPi header pin. One board can service the I2C and UART pins (along with a couple of GPIO) and another board can service SPI pins. BCM GPIO's 13, 16, 19, 20, 21 and 26 are not accessable with this board.

![picture](https://github.com/charkster/rpi_level_shifter_v1/blob/main/rpi_pinout.png)

Check-out my **PDF** [schematic](https://github.com/charkster/rpi_level_shifter_v1/blob/main/rpi_8x2_v1.pdf) !!

Check-out the CSV [**Bill of Materials**](https://github.com/charkster/rpi_level_shifter_v1/blob/main/rpi_8x2_v1_BOM.csv) !!

**The J3 connector must only have one horizontal jumper!! Either HV_EN or LV_EN, or damage to the RPi pins may occur (you have been warned). Additionally, the J4 connector must only have one horizontal jumper!! The RPI_5V is only available if the level shifter board is at the top of the header, otherwise you will need to jumper wire the 5V to the VEXT pin.**


**UPDATES:**
SPI at 5V is working well to 10MHz with the 1k Ohm pull-up resistors. The matches nicely with the NVT2010PW datasheet. I lowered the pull-up resistors to 500 Ohm and was able to get SPI working at 12MHz. I was not able to run faster than 12MHz at 5V. Power consumption was about 0.5W for both the 0.5k and 1k pull-up resistors.

![picture](https://github.com/charkster/rpi_level_shifter_v1/blob/main/rpi_level_shifter_photo_1.png) 
