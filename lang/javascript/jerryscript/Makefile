include $(TOPDIR)/rules.mk

PKG_NAME:=jerryscript
PKG_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/zoobab/jerryscript.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

#MAKE_FLAGS+=VERBOSE=1

define Package/jerryscript
    MAINTAINER:=zoobab@gmail.com
    TITLE:=jerryscript
    SECTION:=lang
    SUBMENU:=Javascript
    CATEGORY:=Languages
endef

define Package/jerryscript/description
	Ultra-lightweight JavaScript engine for Internet of Things
endef

define Package/jerryscript/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/release.linux-cp_minimal $(1)/usr/bin
endef

$(eval $(call BuildPackage,jerryscript))
