# STM32 Based 12-Channel DC Motor Driver Board @18V Max

STM32F401RCT6 based DC Motor Driver capable of running at 18V MAX.

This board is designed for experimental or low current applications with a max current drive of ~800mA.

Features include:

* Reverse Polarity Protection (with LED indicator)
* 10 X GPIO solder pads (can use standard 2.54mm Dupont Header pins)
* Solder pads for PA5, PA6 & PA7 (SPI; SCK, MISO, MOSI)
* USB Mini Connector
* **All GPIO Inputs / Outputs are rated at 3.3V**
* Small Form Factor (Approx 36mm X 64mm)

<img width="375" alt="STM32F401RCT6 12 Channel DC Motor Driver Board 18V Max" src="https://github.com/gxdeange/STM32-12-Channel-DC-Motor-Driver-18V-Max/assets/57690555/93072906-6caa-4126-975f-7e2a040c264c">

# Motor Driver / MCU Pin Mappings

![image](https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/0c7d6fc8-1cc9-4b90-8401-c74ace43b91a)

![STM32 12-CHANNEL MOTOR : MCU PIN MAPPING](https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/9559372b-2946-4ea1-9e84-6d814d84ad75)

# PROGRAMMING NOTE

This MCU does not use an external crystal. The Internal RC Clock (HSI) must be initialised at the start of your code.


