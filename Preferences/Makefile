include $(THEOS)/makefiles/common.mk

BUNDLE_NAME = LockWidgetsPreferences

$(BUNDLE_NAME)_FILES = LWRootListController.m LWSelectWidgetController.m $(wildcard ctdprefs/*.m)
$(BUNDLE_NAME)_INSTALL_PATH = /Library/PreferenceBundles
$(BUNDLE_NAME)_LIBRARIES = lockwidgets
$(BUNDLE_NAME)_FRAMEWORKS = UIKit
$(BUNDLE_NAME)_PRIVATE_FRAMEWORKS = Preferences
$(BUNDLE_NAME)_CFLAGS = -fobjc-arc

export SYSROOT = $(THEOS)/sdks/iPhoneOS14.4.sdk
export ARCHS = arm64 arm64e:x11 arm64e
TARGET = iphone::8.0
TARGET_LIPO=/usr/local/bin/plipo
X11.THEOS_PLATFORM_SDK_ROOT=/Applications/Xcode_117.app/Contents/Developer

include $(THEOS_MAKE_PATH)/bundle.mk

internal-stage::
	$(ECHO_NOTHING)mkdir -p $(THEOS_STAGING_DIR)/Library/PreferenceLoader/Preferences$(ECHO_END)
	$(ECHO_NOTHING)cp entry.plist $(THEOS_STAGING_DIR)/Library/PreferenceLoader/Preferences/LockWidgetsPreferences.plist$(ECHO_END)
