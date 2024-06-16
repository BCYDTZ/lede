include $(TOPDIR)/rules.mk

PKG_NAME:=qca-ssdk-shell
<<<<<<< HEAD
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL:=https://git.codelinaro.org/clo/qsdk/oss/ssdk-shell.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2023-10-04
=======
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2023-10-04
PKG_SOURCE_URL:=https://git.codelinaro.org/clo/qsdk/oss/ssdk-shell.git
>>>>>>> 89db9c40509bda3bd27abc3730822cec52c0fb00
PKG_SOURCE_VERSION:=451c3a26e366ea1acdb4305999a72a0389e74fed
PKG_MIRROR_HASH:=e2da723c12120096f1c851808b868abe1affa14e4d969eff7bedb1e1eb984418

include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

define Package/qca-ssdk-shell
<<<<<<< HEAD
  SECTION:=QCA
  CATEGORY:=Utilities
  TITLE:=Shell application for QCA SSDK
endef


=======
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Shell application for QCA SSDK
  DEPENDS:=@(TARGET_qualcommax)
endef

>>>>>>> 89db9c40509bda3bd27abc3730822cec52c0fb00
define Package/qca-ssdk-shell/Description
  This package contains a qca-ssdk shell application for QCA chipset
endef

ifndef CONFIG_TOOLCHAIN_BIN_PATH
CONFIG_TOOLCHAIN_BIN_PATH=$(TOOLCHAIN_DIR)/bin
endif

<<<<<<< HEAD
QCASSDK_CONFIG_OPTS+= TOOL_PATH=$(CONFIG_TOOLCHAIN_BIN_PATH) \
=======
QCASSDK_CONFIG_OPTS+= \
                TOOL_PATH=$(CONFIG_TOOLCHAIN_BIN_PATH) \
>>>>>>> 89db9c40509bda3bd27abc3730822cec52c0fb00
                SYS_PATH=$(LINUX_DIR) \
                TOOLPREFIX=$(TARGET_CROSS) \
                KVER=$(LINUX_VERSION) \
                CFLAGS="$(TARGET_CFLAGS)" \
                LDFLAGS="$(TARGET_LDFLAGS)" \
                ARCH=$(LINUX_KARCH)

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) $(strip $(QCASSDK_CONFIG_OPTS))
endef

define Package/qca-ssdk-shell/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/bin/ssdk_sh $(1)/usr/sbin/
endef

<<<<<<< HEAD

=======
>>>>>>> 89db9c40509bda3bd27abc3730822cec52c0fb00
$(eval $(call BuildPackage,qca-ssdk-shell))
