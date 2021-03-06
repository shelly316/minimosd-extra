# Arduino Make file. Refer to https://github.com/sudar/Arduino-Makefile

# if you have placed the alternate core in your sketchbook directory, then you can just mention the core name alone.
#ALTERNATE_CORE = atmega
# If not, you might have to include the full path.
#ALTERNATE_CORE_PATH = /home/sudar/Dropbox/code/arduino-sketches/hardware/attiny/

#ARCHITECTURE = STM32F4
#BOARD_TAG    = discovery_f407
#F_CPU = 168000000
#VARIANT    = standard

BOARD_TAG  ?= atmega328
VARIANT     = standard
F_CPU = 16000000



OPT  = -ffast-math 
#OPT += -floop-strip-mine
OPT += -finline-functions-called-once 
OPT += -finline-small-functions
OPT +=  -fno-data-sections -fmerge-all-constants -fmerge-constants
OPT += -fomit-frame-pointer 
OPT += -fno-optimize-sibling-calls 
OPT += -fno-early-inlining 
OPT += -fno-aggressive-loop-optimizations

#OPT += -fmodulo-sched 
#OPT += -fmodulo-sched-allow-regmoves 
OPT += -fassociative-math -freciprocal-math -fno-signed-zeros -fno-trapping-math -fsingle-precision-constant
#OPT += -fconserve-stack
#OPT += -freorder-blocks-and-partition size more
#OPT += -fno-signed-zeros
#OPT += -fearly-inlining 
#OPT += -floop-nest-optimize 
#OPT += -fgcse 
#OPT += -fgcse-sm 
#OPT += -fgcse-las 
#OPT += -fgcse-after-reload 
#OPT += -fdeclone-ctor-dtor 
#OPT += -ftree-pre 
#OPT += -ftree-partial-pre 
#OPT += -fipa-pta +100b
#OPT += -ftree-tail-merge 
#OPT += -fivopts 
#OPT += -fpredictive-commoning
# OPT += -foptimize-strlen
#OPT +=  -fdelayed-branch  not supported
#OPT += -frename-registers  size more
#OPT += -fbranch-target-load-optimize 
#OPT += -fbranch-target-load-optimize2 

# OPT += -ffloat-store   much more
#OPT += -maccumulate-args more size

#nothing
#OPT += -faggressive-loop-optimizations 
#OPT += -fauto-inc-dec  
#OPT += -fbranch-probabilities 
#OPT +=  -floop-strip-mine 
#OPT +=  -fpack-struct 

#OPT += -freciprocal-math 
#OPT += -fno-partial-inlining 
#OPT += -fno-inline-small-functions

OPT +=  -fno-caller-saves
OPT +=  -funsigned-bitfields

#OPT +=   -fno-keep-static-consts -fgcse-sm -fgcse-las -fgcse-after-reload -fdelete-null-pointer-checks

#OPT +=   -fdevirtualize-speculatively -free -fira-region=one -fira-loop-pressure -fconserve-stack -ftree-partial-pre 

OPT +=  -fipa-pta  -fwrapv
# -fno-math-errno
#-fisolate-erroneous-paths-attribute -ftree-loop-distribute-patterns -fivopts -fpredictive-commoning -fstrict-aliasing
#-fdevirtualize-at-ltrans

OPT +=  -fno-strict-aliasing

OPT +=  -fverbose-asm

OPT += $(PROTO)

OPT += -mcall-prologues 
# http://www.nongnu.org/avr-libc/user-manual/FAQ.html
OPT +=  -Wl,--relax 

# OPT += -mbranch-cost=1  #bad
#OPT += -flto -fuse-linker-plugin


#OPT += -v -save-temps # for GCC bugreport


ARDUINO_HEADER = dummy_header.h
USER_LIB_PATH =  ../libraries
CXXFLAGS_STD = -Wno-deprecated-declarations -std=gnu++11  -fno-exceptions -Wl,--gc-sections -fno-threadsafe-statics $(OPT) -felide-constructors -std=c++0x -fconserve-space -fno-enforce-eh-specs -fno-rtti -fvisibility-inlines-hidden -fno-use-cxa-atexit
CFLAGS_STD =  -fno-exceptions  -Wl,--gc-sections  $(OPT) 
LDFLAGS = $(OPT) 
LDFLAGS += -Wl,-Map -Wl,$(OBJDIR)/map.map -Wl,--cref -fwhole-program
MCU ?= atmega328p
#ARFLAGS=--plugin=/usr/share/arduino/hardware/tools/avr/libexec/gcc/avr/5.3.0/liblto_plugin.so

ARDUINO_LIBS = SingleSerial
ARDUINO_LIBS += FastSerial
ARDUINO_LIBS += GCS_MAVLink
ARDUINO_LIBS += TimerSerial
#ARDUINO_LIBS += I2c_soft_slave

include /usr/share/arduino/Arduino.mk

# !!! Important. You have to use make ispload to upload when using ISP programmer
