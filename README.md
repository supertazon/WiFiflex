# WiFiflex
Wii WiFi relocation flex pcb

![WiFiflex](https://github.com/supertazon/WiFiflex/assets/1402795/6885cdbe-66b2-4bac-8e6b-58b71c2bb4f8)
![IMG_3469](https://github.com/supertazon/WiFiflex/assets/1402795/b5aa3793-8d84-407c-8988-c64485fead5c)

A flex pcb to easily relocate the Wii WiFi chip for Wii portables (useless for stock Wii) by using the WiFi chip connector. The WiFi chip is notorious for being difficult to relocate by handwiring it due to wire length sensitivity. License is permissive, you are free to make, sell and distribute the flex pcb.

The flex pcb is compatible with a OMGWTF trim, it also does not overlap with the NAND relocation flex.

Repo contains the KiCad source files (needs KiCad 7.99 minimum to work) and gerbers.

**BOM**

Molex connector 52991-0208: [DigiKey](https://www.digikey.com/en/products/detail/molex/0529910208/1059850) or [Mouser](https://www.mouser.com/ProductDetail/Molex/52991-0208?qs=KC2ywxza1krtfqlg7H04kw%3D%3D)

## How to order

[YveltalGriffin](https://github.com/mackieks) suggested to order the flex pcb from PCBWay rather than other providers as this flex uses small castellation vias and PCBWay properly handles them. You can try ordering it from JLCPCB or any other service but at your own risk.

  - FPC thickness: 0.1 mm
  - min hole size: >0.15/0.35mm
  - Surface finish:  Immersion gold (ENIG) (1U")
  - min track spacing: ≥ 0.06mm
  - Finished copper:  0.5 oz Cu (18μm)


## How to install

  1. Populate the flex pcb, take note of the silkscreen to correctly position the connector. I highly recommend using solder paste and a hot plate or hot air, it's definitely easier than hand soldering it. Check continuity between the connector pins and the vias before moving on.
  2. Scratch the two pairs of vias 3.3V and GND while making sure to scratch the space between both.
  3. Position the flex to locate where you will scratch the Wii's GND plane for the upper right via on the flex.
  4. Scratch the Wii's GND plane at the correct position.
![image](https://github.com/supertazon/WiFiflex/assets/1402795/c1d43988-1366-4a60-a345-c4a0bf6e58f1)
*Vias and GND spot scratched, could have done better but wanted to avoid scratching the surrounding traces*

  6. Add flux and pre-tin the vias and GND spot. I noticed the 3.3V vias needed more heat to be properly tinned.
  7. Position the flex and secure it with a piece of kapton tape between the GND vias and the connector.
  8. Solder the GND vias with the Wii GND vias and the 3.3V vias with the Wii's 3.3V vias. Don't forget you might need to apply more heat on the 3.3V vias.
  9. Add flux and solder to the resistors.
  10. Check continuity between the resistors and the according connector pins.
  11. If everything is nominal then proceed with soldering the big GND via, otherwise reflow as needed.

Now that you are done you can try putting a WiFi chip on there and see if you get signal. Becareful to not short anything on the board, you might need to add kapton tape either on the chip or on the Wii motherboard.

### Please handle the flex pcb with care! It is quite fragile, I inadvertently ripped it off the Wii while testing. Make sure you really solder that big GND via for better stability.

## Contributors

- **supertazon**: Initial design and routing
- **[YveltalGriffin](https://github.com/mackieks)**: Via stitching, large GND via addition and general tips on routing

## Acknowledgements

- [Shank's Definitive Wii Trimming Guide](https://bitbuilt.net/forums/index.php?threads/the-definitive-wii-trimming-guide.198/): for info on WiFi soldering points
- [MJMT's WiFi breakout board](https://bitbuilt.net/forums/index.php?threads/wifi-breakout-board-for-relocation.4916/post-53366): for the connector reference
- [ShockSlayer's handwired WiFi relocation](https://bitbuilt.net/forums/index.php?threads/sswiit-revitalized.146/post-982): to see how it was done before
