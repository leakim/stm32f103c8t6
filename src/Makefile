
install:
	echo "need gcc 4.8.x, due to broken optimizations in 4.9.x"
	sudo cp stm32.list /etc/apt/sources.list.d/
	sudo apt-get update
	sudo apt-get install gcc-arm-none-eabi=4.8.3-18ubuntu2+12

git:
	git clone https://github.com/rogerclarkmelbourne/STM32duino-bootloader.git

maple-mini:
	make -C STM32duino-bootloader/STM32F1 clean
	make -C STM32duino-bootloader/STM32F1 maple-mini
	cp   -v STM32duino-bootloader/STM32F1/binaries/maple_mini_boot20.bin .

ocd:
	sudo openocd -f /usr/share/openocd/scripts/interface/stlink-v2.cfg -f /usr/share/openocd/scripts/target/stm32f1x.cfg 2>&1 | tee openocd.out

cli:
	telnet 127.0.0.1 4444

