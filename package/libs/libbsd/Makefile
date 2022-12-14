include $(TOPDIR)/rules.mk

PKG_NAME:=libbsd
PKG_VERSION:=0.11.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://libbsd.freedesktop.org/releases
PKG_HASH:=19b38f3172eaf693e6e1c68714636190c7e48851e45224d720b3b5bc0499b5df

PKG_LICENSE:=BSD-4-Clause
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1
PKG_BUILD_DEPENDS := libmd

include $(INCLUDE_DIR)/package.mk

define Package/libbsd
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=common BSD library
  ABI_VERSION:=0
endef

define Package/libbsd/description
 This library provides useful functions commonly found on BSD systems, and lacking on others like GNU systems, thus making it easier to port projects with strong BSD origins, without needing to embed the same code over and over again on each project.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libbsd.{la,so*} $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libbsd*.pc $(1)/usr/lib/pkgconfig/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
endef

define Package/libbsd/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libbsd.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libbsd))
