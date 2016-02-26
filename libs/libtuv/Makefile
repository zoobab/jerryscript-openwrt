include $(TOPDIR)/rules.mk

PKG_NAME:=libtuv
PKG_VERSION:=df9f328
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Samsung/libtuv
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=df9f328ad3d6426169ef1fcefa6c332a3168a8bf
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_MAINTAINER:=Benjamin Henrion <zoobab@gmail.com>
PKG_LICENSE=WTFPL
PKG_INSTALL:=0
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

TARGET_CFLAGS:=$(filter-out -Werror, $(TARGET_CFLAGS))

CMAKE_OPTIONS+=-DTARGET_PLATFORM="linux_common" -DCMAKE_BUILD_TYPE="debug" -DBUILDTESTER="no" -DBUILDAPIEMULTESTER="no" -DLIBTUV_CUSTOM_LIB_OUT="$(PKG_BUILD_DIR)"

define Package/libtuv
  MAINTAINER:=zoobab@gmail.com
  TITLE:=libtuv
  SECTION:=libs
  CATEGORY:=Libraries
  SUBMENU:=IoT
  TITLE:=Asynchronous I/O for IoT.js and embedded system
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)
endef

define Build/Install
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/libtuv.a $(PKG_INSTALL_DIR)/usr/lib/libtuv.a
endef

define Package/libtuv/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libtuv))
