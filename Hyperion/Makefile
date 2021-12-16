include $(THEOS)/makefiles/common.mk

BUNDLE_NAME = LockWidgetsHyperion
$(BUNDLE_NAME)_LIBRARIES = lockwidgets
$(BUNDLE_NAME)_CFLAGS = -fobjc-arc
$(BUNDLE_NAME)_FILES = $(wildcard *.m) $(wildcard *.mm)
$(BUNDLE_NAME)_FRAMEWORKS = UIKit
$(BUNDLE_NAME)_INSTALL_PATH = /Library/Hyperion/Widgets

export SYSROOT = $(THEOS)/sdks/iPhoneOS14.4.sdk
export ARCHS = arm64 arm64e:x11 arm64e
TARGET = iphone::8.0
TARGET_LIPO=/usr/local/bin/plipo
X11.THEOS_PLATFORM_SDK_ROOT=/Applications/Xcode_117.app/Contents/Developer

include $(THEOS_MAKE_PATH)/bundle.mk

BUNDLE_PATH = $($(BUNDLE_NAME)_INSTALL_PATH)/$(BUNDLE_NAME).bundle

internal-stage::
	$(ECHO_NOTHING)mkdir -p $(THEOS_STAGING_DIR)$(BUNDLE_PATH)$(ECHO_END)
	$(ECHO_NOTHING)cp Info.plist $(THEOS_STAGING_DIR)$(BUNDLE_PATH)/Info.plist$(ECHO_END)
	$(ECHO_NOTHING)cp Preferences.plist $(THEOS_STAGING_DIR)$(BUNDLE_PATH)/Preferences.plist$(ECHO_END)

after-install::
	install.exec "killall -9 SpringBoard"
