obj-m += lkm_example.o

# if the module spans across multiple files:
# obj−m += hello−4.o
# obj−m += hello−5.o
# obj−m += startstop.o
# startstop−objs := start.o stop.o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean

#test:
#	sudo dmesg -C
#	sudo insmod lkm_example.ko
#	sudo rmmod lkm_example
#	dmesg

test:
	# the leading - tells make to ignore an error in case the module isn't loaded
	-sudo rmmod lkm_example
	# clear the kernel log
	sudo dmesg -C
	# insert the module
	sudo insmod lkm_example.ko
	# display the kernel log
	dmesg
