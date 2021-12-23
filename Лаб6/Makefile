ifneq ($(KERNELRELEASE),)
# kbuild part of makefile
obj-m := Lab5.o
ccflags-y := -I$(src)/inc -g
else
# normal makefile
KDIR ?= /lib/modules/`uname -r`/build

default:
	$(MAKE) -C $(KDIR) M=$$PWD
	cp Lab5.ko Lab5.ko.unstripped
	$(CROSS_COMPILE)strip -g Lab5.ko

clean:
	$(MAKE) -C $(KDIR) M=$$PWD clean

%.s %.i: %.c
	$(MAKE) -C $(KDIR) M=$$PWD $@

endif
