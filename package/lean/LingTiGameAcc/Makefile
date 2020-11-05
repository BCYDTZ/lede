#
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v3.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=LingTiGameAcc
PKG_VERSION:=20200718
PKG_RELEASE:=4

PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=eSir Playground

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  CATEGORY:=Network
  TITLE:=LingTi Game Accelerator
  URL:=https://github.com/esirplayground/LingTiGameAcc
  DEPENDS:=+kmod-tun
endef

define Package/$(PKG_NAME)/description
LingTi Game Acc is a Game Accelerator which is paid service.
endef

ifeq ($(ARCH),x86_64)
	ADBYBY_DIR:=x86_64
endif
ifeq ($(ARCH),mipsel)
	ADBYBY_DIR:=mipsle
endif
ifeq ($(ARCH),mips)
	ADBYBY_DIR:=mips
endif
ifeq ($(ARCH),i386)
	ADBYBY_DIR:=x86_64
endif
ifeq ($(ARCH),arm)
	ADBYBY_DIR:=armv7
	ifeq ($(BOARD),bcm53xx)
		ADBYBY_DIR:=arm
  endif
  ifeq ($(BOARD),kirkwood)
		ADBYBY_DIR:=arm
  endif
endif
ifeq ($(ARCH),aarch64)
	ADBYBY_DIR:=armv7
endif

define Build/Prepare
	mkdir $(PKG_BUILD_DIR)/$(PKG_NAME)
	cp -r ./files/$(DIR_ARCH)/* $(PKG_BUILD_DIR)/$(PKG_NAME)/lingti
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME)/lingti $(1)/usr/bin


	$(INSTALL_DIR) $(1)/etc/init.d 
	$(INSTALL_BIN) ./root/etc/init.d/lingti $(1)/etc/init.d
endef

define Package/coremark/postinst
#!/bin/sh
chmod +x $(1)/usr/bin/lingti
chmod +x $(1)/etc/init.d/lingti
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
