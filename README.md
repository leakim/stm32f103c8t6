

# stm32f103c8t6
Having fun with OpenOCD, ST-Link V2 and a STM32F103C8T6 dev board (STM32_Smart v2.0)

See results, photos, notes and more in the [wiki](https://github.com/leakim/stm32f103c8t6/wiki) 

Spec
----
```
ARM Cortex M3 @ 72MHz (32-bit
64k Flash (0x0800 0000 - 0x0800 ffff)
20k SRAM  (0x2000 0000 - 0x2000 4fff)
I/O       (0x4000 0000 - 0x4002 3400)
system    (0x1fff f000 - 0x1fff f800)
```


This is what to do
------------------
```
cd src
sudo cp stm32.list /etc/apt/sources.list.d/
sudo apt-get update
make install # will install correct gcc-arm-none-eabi
make git
make maple-mini
make ocd
```

and in a second terminal

```
cd src
make cli
> reset halt
...
> dump_image dump.bin 0x8000000 0x1ffff
...
> flash write_image erase maple_mini_boot20.bin 0x08000000
...
> reset run
> exit
```


