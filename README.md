# tc1126 
tc1126 cn1100 tcm1680 Touch screen driver 

Compile with kernel 4.14 mainline.

Does not support Devicetree for now (you must put resolution, irq and wakeup pin in code).

$$
Put folder tc1126 in  $kernelpath/drivers/input/touchscreen/$

add: 

source "drivers/input/touchscreen/tc1126/Kconfig"

at end of file 

$kernelpath/drivers/input/touchscreen/Kconfig

add

obj-$(CONFIG_TOUCHSCREEN_TC1126_TS) += tc1126/

at the end of 

$kernelpath/drivers/input/touchscreen/Makefile


activate module (eg with menuconfig )

compile kernel 

to istance driver  add in dts file of your hardware


&i2cX {
        // Touch Screen
        tc1126@20 {
                compatible = "tc1126";
                reg = <0x20>;
                //interrupt-parent = <&pio>;
                //interrupts = <1 5 IRQ_TYPE_EDGE_RISING>; // PB05 
        };
};

with X = I2C bus number.
