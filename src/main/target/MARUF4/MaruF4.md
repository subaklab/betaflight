# MARUF4

This targets supports various variants of brushed and brushless flight controllers. The designs for them are released partially for public use at:

http://www.subak.io/maruf4

All published designs are flight tested by various people. The intention here is to make these flight controllers available and enable skilled users or RC vendors to build this designs.

This controllers will be available for purchase from:

http://www.subak.io/maruf4

Here are the general hardware specifications for this boards:

- STM32F405RGT6 MCU
- MPU9250/ICM-20608-G accelerometer/gyro(/mag) sensor unit
- The MPU sensor interrupt is connected to the MCU for all new F4 design and enabled in the firmware
- USB port, integrated
- (*) serial connection for external DSM2/DSMX sat receiver (e.g. Spektrum SAT, OrangeRx R100, Lemon RX or Deltang Rx31) and SBUS
- CPPM input
- ground and 3.3V for the receiver, some boards have also the option to power an 5V receiver
- hardware bind plug for easy binding
- motor connections are at the corners for a clean look with reduced wiring
- small footprint
- direct operation from a single cell Lipoly battery for brushed versions
- 3.3V LDO power regulator (older prototypes)
- 3.3V buck-boost power converter (all new versions)
- 5V buck-boost power converter for FPV (some versions)
- brushless versions are designed for 3S operation and also have an 5V power output
- battery monitoring with an LED for buzzer functionality

(*) Spektrum Compatible DSM2 satellites are supported out of the box. DSMX sat will work with DSM2 protocol with default settings (DSM2, 11bit, 11ms is preset). This is chosen for maximum compatibility. For optimal connection it is recommended to adjust settings to match the capabilities of your transmitter and satellite receiver. If possible it is recommended to use the DSMX protocol since it is known as more reliable. Also to make use of additional channels you should adjust the following two parameters with the Cleanflight Configurator.

    set serialrx_provider = 1   (0 for 1024bit, 1 for 2048bit) 
    set spektrum_sat_bind = 5
    
For more detail of the different bind modes please refer the CleanFlight Spektrum Bind document.

Deltang receivers in serial mode will work like any other Spektrum satellite receiver (10bit, 22ms) only the bind process will be different. 

## Flashing the firmware

The firmware can be updated with the BetaFlight configurator as for any other target. This board has a boot jumper which need to be closed for initial flashing or for recovery from a broken firmware.
