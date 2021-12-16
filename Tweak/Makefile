INSTALL_TARGET_PROCESSES = SpringBoard

include $(THEOS)/makefiles/common.mk

TWEAK_NAME = LockWidgets

LockWidgets_FILES = Tweak.xm LockWidgetsManager.m
LockWidgets_CFLAGS = -fobjc-arc
LockWidgets_LIBRARIES = lockwidgets

export SYSROOT = $(THEOS)/sdks/iPhoneOS14.4.sdk
export ARCHS = arm64 arm64e:x11 arm64e
TARGET = iphone::8.0
TARGET_LIPO=/usr/local/bin/plipo
X11.THEOS_PLATFORM_SDK_ROOT=/Applications/Xcode_117.app/Contents/Developer

include $(THEOS_MAKE_PATH)/tweak.mk
