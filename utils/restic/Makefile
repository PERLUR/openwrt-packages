#
# Copyright (C) 2018 PERLUR Group
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=restic
PKG_VERSION:=0.9.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/restic/restic/releases
PKG_HASH:=8f8eee3e9651b9f7384a323ba3c26a5667a6388ab2ef8e6d869d3cd69b9f7c95

PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/restic/Default
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Backup
  DEPENDS:=
  TITLE:=restic - Fast, secure, efficient backup program
  URL:=https://restic.net/
endef

define Package/restic
  $(call Package/restic/Default)
  MENU:=1
endef

define Package/restic/description

endef


CONFIGURE_ARGS += \
	--disable-rpath \


MAKE_FLAGS += \
	SUBDIRS="m4 intl zlib util mpi cipher tools g10 keyserver ${checks}" \


define Package/restic/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/gpg $(1)/usr/bin/
endef


$(eval $(call BuildPackage,restic))