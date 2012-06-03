all:
	../contrib/pspgz.py usbdevice.prx ../contrib/SystemControl.hdr usbdevice.prx pspUsbDev_Driver 0x1006

TARGET = usbdevice
OBJS = main.o exports.o

INCDIR =  -I ../include
CFLAGS = -Os -G0 -Wall -fshort-wchar -fno-pic -mno-check-zero-division 
CXXFLAGS = $(CFLAGS) -fno-exceptions -fno-rtti
ASFLAGS = $(CFLAGS)

ifeq ($(DEBUG), 1)
CFLAGS += -DDEBUG=1
OBJS += ../Common/printk.o
else
endif

ifeq ($(CONFIG_620), 1)
CFLAGS += -DCONFIG_620=1
PSP_FW_VERSION = 620
endif

ifeq ($(CONFIG_635), 1)
CFLAGS += -DCONFIG_635=1
PSP_FW_VERSION = 635
endif

ifeq ($(CONFIG_639), 1)
CFLAGS += -DCONFIG_639=1
PSP_FW_VERSION = 639
endif

ifeq ($(CONFIG_660), 1)
CFLAGS += -DCONFIG_660=1
PSP_FW_VERSION = 660
endif

BUILD_PRX = 1
PRX_EXPORTS = exports.exp

USE_KERNEL_LIBC = 1
USE_KERNEL_LIBS = 1


LIBDIR = ../libs
LIBS = -lpspsystemctrl_kernel -lpspumd_kernel

PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build_prx.mak
