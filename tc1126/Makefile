#
# Makefile for the touchscreen drivers.
#


DRIVER=cn1100

obj-$(CONFIG_TOUCHSCREEN_TC1126_TS)       += tc1126_ts.o
tc1126_ts-objs := $(DRIVER).o  debug_proc.o TC1126_data.o TC1126_hwService.o

