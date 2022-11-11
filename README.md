# DF Robot DFR0928 LCD display drivers for Raspberry Pi

## Instructions for builidng and installing

1. Copy files to folder on Pi.
2. Run 'make'. This will build the dfr0928.ko file.
3. Run 'sudo cp software/driver/dfr0928.ko /usr/lib/modules/5.15.74-v7+/kernel/drivers/' (may need to modify Linux version string).
4. Run 'sudo depmod'.
5. Add the following line to your /boot/config.txt file (modify the parameters as required):
dtoverlay=dfr0928,dc_pin=27,reset_pin=22,led_pin=17,rotate=270
6. Run 'dtc -O dtb -o dfr0928.dtb dfr0928.dts'.
7. Run 'sudo cp dfr0928.dtb /boot/overlays/dfr0928.dtbo'.

Now reboot and enjoy your display!
