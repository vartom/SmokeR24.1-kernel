# Custom kernel for Xiaomi MiPad 1 (MOCHA)
# Kernel version 3.10.108

You need to flash tos.img in order for all 4 cores to work otherwise only one core will work!
Work only with shieldtablet blobs.

=========================================================================
* Works:
	* LCD panel
	* Touch Screens
	* Charger
	* Wi-fi
	* BT
	* FM
	* Button-backlight
	* Brightness
	* Leds
	* Sensors
	* Vibrator
	* Battery
	* Camera
	* Sound
	* OTG
	* PSCI 0.2

=========================================================================
# BUILD
export ARCH=arm

export CROSS_COMPILE=arm-linux-gnueabihf-

make mocha_android_defconfig

make -j4 zImage

make tegra124-mocha.dtb

# Busses
* I2C0:
	* lp8556 	            	(002c)
	* lsm6db0 	            	(0008)
	* isl29035           		(0044)
	* lp5521    				(0032)
	* rt5671          			(001c)
	* tfa9890					(0034)
	* tfa9890					(0037)
* I2C1:
	* bq2419x					(006b)
	* bq27520           		(0055)
* I2C2:
	* IMX179 					(0010)
	* AD5823					(000c)
	* OV5693					(0036)
* I2C3:
	* synaptics 7040        	(0020)
	* mxt1664t or mxt1066t		(004a)
* I2C4:
	* tps65913 					(0058)			
* SDHCI0:
	* BCM4354
* SDHCI2:
	* Micro-SDcard reader
* SDHCI3:
	* EMMC

# AUTHORS:
* Insei(DbIm)
* arttttt(ArtemkaVZM or fvckdattrap)

# Original kernel by:
* Nvidia
