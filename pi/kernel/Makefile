# If KERNELRELEASE is defined, we've been invoked from the
# kernel build system and can use its language.
MODNAME=hello
ifneq ($(KERNELRELEASE),)
	obj-m := $(MODNAME).o
# Otherwise we were called directly from the command
# line; invoke the kernel build system.
else
	KERNELDIR ?= /lib/modules/$(shell uname -r)/build
	KERNELDIR ?= raspberrypi
	PWD := $(shell pwd)
default:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules


ins:	
	sudo insmod $(MODNAME).ko

rmod:	
	sudo rmmod $(MODNAME).ko

endif
