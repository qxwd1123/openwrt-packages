#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PECL_NAME:=redis
PECL_LONGNAME:=PHP extension for interfacing with Redis

PKG_VERSION:=6.0.2
PKG_RELEASE:=1
PKG_HASH:=01aeccb0e14f897fe56f0509be6e6991ff0ad459f9d34e95e4556d02699b9a03

PKG_NAME:=php8-pecl-redis
PKG_SOURCE:=$(PECL_NAME)-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=https://pecl.php.net/get/

PKG_MAINTAINER:=Michael Heimpold <mhei@heimpold.de>

PKG_LICENSE:=PHP-3.01
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include ../php8/pecl.mk

CONFIGURE_ARGS+= \
	--enable-redis \
	--enable-redis-json \
	--disable-redis-igbinary \
	--disable-redis-lzf \
	--disable-redis-msgpack

$(eval $(call PHP8PECLPackage,$(PECL_NAME),$(PECL_LONGNAME),+php8-mod-session,25))
$(eval $(call BuildPackage,$(PKG_NAME)))
