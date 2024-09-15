# SqueezeAMPagain

## The Plan
Another board for [Squeezelite-esp32](https://github.com/sle118/squeezelite-esp32)


Inspired by [SqueezeAMP](https://github.com/philippe44/SqueezeAMP)  and [SqueezeAmpToo](https://github.com/rochuck/squeeze-amp-too)
with the goal of beeing able to order a SMD pre-placed PCB from JLCPCB.

As JLCPBCs offer in inductors and electrolytic caps is not satisfying (limited availability in extended parts) inductors and caps need to be placed separately.

This is a work in progress. While the first pcbs are made they contain bugs:
 - accidentially conencted CPVSS to 3V3
 - Forgot a bypass solderjumper for Q2

Please check the dev branch for corrected schematics.

- Improved / modified pinning (requires new config) 
  - added MCLK
    - should not be needed / check if it can benefit from it
  - power management
    - switchable power to TAS
      - lower standby consumption by 200mW
      - PVDD: currently resets the powersupply when the caps charge 
        - add precharge?
      - 3V3: current squeezelite does not start up correctly if the amp is not powered
    - switchable power to MCU 
      - true Power off
      - Wake detect / power on needs to be implemented

  - only use normal power supply (no battery) 
    - extra connector for optional power
  
- optionally use a RP2040 based board
  - untested
- optionally use a Raspberry pi
  - reported working
- optional heat spreader / sink bottom side


## Findings / TODO

- Esp32-wrover modules are available for placing at JLCPCB, just not in the "economic" placing program.
  - create a better footprint to easily solder the module (with exposed pads)
- Test if use of smaller inductors are possible
- ~~5V Regulator humms without load @ 200 Hz, 0,5Vpp~~
  - fixed by removing C71
- internal pullup for BOOT might be too weak.
- GND test connection can be thermals instead of full

