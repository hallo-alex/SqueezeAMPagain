# SqueezeAMPagain

## The Plan
Another board for [Squeezelite-esp32](https://github.com/sle118/squeezelite-esp32)


Inspired by [SqueezeAMP](https://github.com/philippe44/SqueezeAMP)  and [SqueezeAmpToo](https://github.com/rochuck/squeeze-amp-too)
with the goal of beeing able to order a SMD pre-placed PCB from JLCPCB.

As JLCPBCs offer in inductors and electrolytic caps is not satisfying (limited availability in extended parts) inductors and caps need to be placed separately.

This is a work in progress with the goal of

- Improved pinning (requires new config) 
  - added MCLK
  - only use normal power supply (no battery) 
    - extra connector for optional power
- optionally use a RP2040 based board
- optionally use a Raspberry pi
- optional heat spreader / sink bottom side


## Findings / TODO

- Esp32-wrover modules are available for placing at JLCPCB, just not in the "economic" placing program.
  - create a better footprint to easily solder the module (with exposed pads)
- Test if use of smaller inductors are possible
- 5V Regulator humms without load @ 200 Hz, 0,5Vpp
  - 3V
- GND test connection can be thermals instead of full

