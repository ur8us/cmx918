# cmx918
DRM1000 module based on the CMX918 DRM tuner

"Covers broadcast bands from 530 kHz to 108 MHz."

[Module datasheet](https://cmlmicro.com/Content/Downloads/DRM1000Datasheet.pdf)

DRM1000 teardown:

![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/IMG_2935.JPG)
  
See other photos in the [IMAGES](https://github.com/ur8us/cmx918/tree/main/IMAGES) folder.
  
Chips:

- U1: CMX918 (CMX918Q5) - DRM tuner (no datasheet available)
Structure diagram:
![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/cmx918-structure.png)
  
- U2: CMX655D - Audio codec [Info](https://cmlmicro.com/products/digital-voice/product/cmx655d-ultra-low-power-voice-codec)
- U3: HX6537-A - Mircocontroller [Datasheet](https://www.himax.com.tw/product-brief/HX6537.39.40-A_product_brief.pdf)
- U4: ?
- U5: ?
  
Test points, top:

- TP20 - ?
- TP2? - ?
  
Test points, bottom:

- TP1 - internal I2C SCK
- TP4 - internal I2C DATA
  
I2C addresses: CMX918 - 0x55, CMX655D - 0x57
  
- TP2 - ?
  
Digital data from the CMX918:
- TP9 - bit clock (15360 kHz in FM, 7680 kHz in VHF DRM, 768 kHz in AM and HF DRM) - connected to pin 41 of the microcontroller, PSPI_SCLK
- TP10 - sample clock (480 kHz in FM, 240 kHz in VHF DRM, 24 kHz in AM and HF DRM) - connected to pin 38 of the microcontroller, PSPI_CS0
- TP11 - data (32 bits per sample) - connected to pin 39 of the microcontroller, PSPI_SDIO0
  
Bit clock and sample clock at 24 kHz sample rate:
![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/cmx918-osc24k.png)
  
There are non-populated resistors on the module, which connect pins 27, 29, 28 to TP9, TP10, TP11.
  
- TP12 - ?
- TP16 - ?
  
I2S to the codec chip:
- TP22 - bit clock (2048 kHz in FM and VHF DRM, 1024 kHz in AM and HF DRM)
- TP28 - data (64 bits per sample)
- TP29 - L/R clock (32 kHz in FM and VHF DRM, 16 kHz in AM and HF DRM)
  
- TP24 - ?
- TP25 - ?
- TP26 - ?
- TP27 - ?
- TP30 - ?

# Registers of the CMX918

- 0xD1, 0xD0 - status, RSSI ? - read every second

# My prototype board

Do not want to buy a "CML Micro DE9180-2 Demo & Prototyping Kit for the DRM1000"? Make it yourself for $10. 
![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/top1.jpeg)
![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/bot1.jpeg)

Now I have access to the internal I2C as well as to the digital data from the CMX918.

