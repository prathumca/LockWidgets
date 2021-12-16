include $(THEOS)/makefiles/common.mk

LIBRARY_NAME = liblockwidgets

liblockwidgets_FILES = LockWidgetsView.mm LockWidgetsConfig.m MRYIPCCenter.m
liblockwidgets_CFLAGS = -fobjc-arc

export SYSROOT = $(THEOS)/sdks/iPhoneOS14.4.sdk
export ARCHS = arm64 arm64e:x11 arm64e
TARGET = iphone::8.0
TARGET_LIPO=/usr/local/bin/plipo
X11.THEOS_PLATFORM_SDK_ROOT=/Applications/Xcode_117.app/Contents/Developer

include $(THEOS_MAKE_PATH)/library.mk

after-all::
	mkdir -p $(THEOS)/include/$(LIBRARY_NAME)
	cp *.h $(THEOS)/include/$(LIBRARY_NAME)
	cp $(THEOS_OBJ_DIR)/$(LIBRARY_NAME).dylib $(THEOS)/lib/$(LIBRARY_NAME).dylib
