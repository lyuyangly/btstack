# Makefile to build example code for all platforms but 
# - iOS (iOS requires double Xcode installation)
# Intended for Continous Integration
#
# Requires:
# - gcc/clang, pkg-config, libusb
# - arm-none-eabi
# - mspgcc
# - Android Native Development Kit
# - Microchip XC32

SUBDIRS =  \
			daemon \
			libusb \
			libusb-intel \
			posix-h4 \

EXCLUDED = \
			windows-h4 \
			windows-winusb \

subdirs:
	echo Building all ports
	for dir in $(SUBDIRS); do \
	  $(MAKE) -C $$dir; \
	done
	echo Building daemon
	cd daemon ; ./bootstrap.sh ; make

clean:
	echo Cleaning all ports
	for dir in $(SUBDIRS); do \
	  $(MAKE) -C $$dir clean; \
	done
	echo Cleaning daemon
	cd daemon ; make clean
