TARGET = kpspident
OBJS = main.o 

INCDIR = ../include
CFLAGS = -Os -G0 -Wall -fno-pic
CXXFLAGS = $(CFLAGS) -fno-exceptions -fno-rtti
ASFLAGS = $(CFLAGS)

ifeq ($(CONFIG_639), 1)
PSP_FW_VERSION = 639
endif

ifeq ($(CONFIG_660), 1)
PSP_FW_VERSION = 660
endif

BUILD_PRX = 1
PRX_EXPORTS = exports.exp

LIBDIR =
LDFLAGS = -mno-crt0 -nostartfiles
LIBS =

USE_KERNEL_LIBC = 1
USE_KERNEL_LIBS = 1

PSPSDK=$(shell psp-config --pspsdk-path)
include $(PSPSDK)/lib/build.mak
