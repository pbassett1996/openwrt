#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=expat
PKG_CPE_ID:=cpe:/a:libexpat:expat
PKG_VERSION:=2.4.8

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_HASH:=a247a7f6bbb21cf2ca81ea4cbb916bfb9717ca523631675f99b3d4a5678dcd16
PKG_SOURCE_URL:=https://github.com/libexpat/libexpat/releases/download/R_$(subst .,_,$(PKG_VERSION))

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_HOST_OPTIONS += \
	-DDOCBOOK_TO_MAN=OFF \
	-DEXPAT_BUILD_TOOLS=OFF \
	-DEXPAT_BUILD_EXAMPLES=OFF \
	-DEXPAT_BUILD_TESTS=OFF \
	-DEXPAT_BUILD_DOCS=OFF \
	-DEXPAT_WITH_LIBBSD=OFF \
	-DEXPAT_ENABLE_INSTALL=ON \
	-DEXPAT_DTD=ON \
	-DEXPAT_NS=OFF \
	-DEXPAT_DEV_URANDOM=OFF

$(eval $(call HostBuild))
