# STM32 Based 12-Channel Brushed DC Motor Driver Board @10V Max

STM32F401RCT6 based Stepper Motor Driver capable of running at 10V MAX.

This board is designed for experimental or low current robotics with a max current drive of ~800mA.

Features include:

Reverse Polarity Protection (with LED indicator)

10 X GPIO solder pads (can use standard 2.54mm Dupont Header pins)

USB Mini Connector

Small Form Factor (Approx 36mm X 64mm)

<img width="392" alt="STM32F401RCT6 12-CHANNEL BRUSHED DC MOTOR DRIVER BOARD @10V MAX" src="https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/1fad41d9-36f8-4809-ae4a-735f471248e5">

# Motor Driver / MCU Pin Mappings

![image](https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/0c7d6fc8-1cc9-4b90-8401-c74ace43b91a)

![STM32 12-CHANNEL MOTOR : MCU PIN MAPPING](https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/9559372b-2946-4ea1-9e84-6d814d84ad75)

# PROGRAMMING NOTE

This MCU does not use an external crystal. The Internal RC Clock (HSI) must be initialised at the start of you sketch.


