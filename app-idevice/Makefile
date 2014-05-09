export DEVELOPER_DIR := $(shell xcode-select --print-path)
SDK_VER_IOS=7.1
SDK_IOS_DEVICE="$(DEVELOPER_DIR)/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS$(SDK_VER_IOS).sdk"
MIN_VER_IOS=-miphoneos-version-min=5.0
ARCH_IOS=-arch armv7
CC_IOS=xcrun -sdk "iphoneos" gcc
CXX_IOS=xcrun -sdk "iphoneos" g++

TARGET=serial-echo
LD=$(CC)
LDFLAGS = -framework CoreFoundation \
          -framework Foundation \
          -framework UIKit \
          -framework LayerKit \
          -framework CoreGraphics \
          -framework GraphicsServices \
          -framework CoreSurface \
          -lobjc

all: serial.c
	$(CC_IOS) -o $(TARGET) serial.c $(ARCH_IOS) $(MIN_VER_IOS) -isysroot $(SDK_IOS_DEVICE) -I$(SDK_IOS_DEVICE)/usr/include -I.
	ldid $(TARGET)

clean:
	rm -f $(TARGET)

