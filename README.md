# cmx918
DRM1000 module based on the CMX918 DRM tuner

"Covers broadcast bands from 530 kHz to 108 MHz."

[Module datasheet](https://cmlmicro.com/Content/Downloads/DRM1000Datasheet.pdf)

DRM1000 teardown:

![Image.](https://github.com/ur8us/cmx918/blob/main/IMAGES/IMG_2935.JPG)

See other photos in the [IMAGES](https://github.com/ur8us/cmx918/tree/main/IMAGES) folder.

Chips:

- U1: CMX918 (CMX918Q5) - DRM tuner (no datasheet available)
- U2: CMX655D - Audio codec [Info](https://cmlmicro.com/products/digital-voice/product/cmx655d-ultra-low-power-voice-codec)
- U3: HX6537-A - Mircocontroller [Datasheet](https://www.himax.com.tw/product-brief/HX6537.39.40-A_product_brief.pdf)
- U4: ?
- U5: ?

Test points, top:

- TP20
- TP2?

Test points, bottom:

- TP1 - internal I2C SCK
- TP4 - internal I2C DATA

I2C addresses: CMX918 - 0x55, CMX655D - 0x57

- TP2

I2S from the CMX918:
- TP9 - bit clock (15360 kHz in FM, 7680 kHz in VHF DRM, 768 kHz in AM and HF DRM)
- TP10 - L/R clock (480 kHz in FM, 240 kHz in VHF DRM, 24 kHz in AM and HF DRM)
- TP11 - data (32 bits per sample)

There are non-populated resistors on the module, which connect pins 27, 29, 28 to TP9, TP10, TP11.

- TP12
- TP16

I2S to the codec chip:
- TP22 - bit clock (2048 kHz in FM and VHF DRM, 1024 kHz in AM and HF DRM)
- TP28 - data (64 bits per sample)
- TP29 - L/R clock (32 kHz in FM and VHF DRM, 16 kHz in AM and HF DRM)

- TP24
- TP25
- TP26
- TP27
  
- TP30
