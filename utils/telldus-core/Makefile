include $(TOPDIR)/rules.mk

PKG_NAME:=telldus-core
PKG_VERSION:=2.1.2
PKG_RELEASE:=1
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://download.telldus.com/TellStick/Software/telldus-core/

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include $(INCLUDE_DIR)/cmake.mk


define Package/telldus-core
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Telldus core app for Telldus USB stick home automation.
	URL:=http://www.telldus.com
	DEPENDS:=+confuse +libftdi +libstdcpp $(ICONV_DEPENDS)
endef


CMAKE_OPTIONS += -DBUILD_TDADMIN=false

define Package/telldus-core/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,telldus-core))
