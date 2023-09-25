#
#-- Copyright (C) 2021 dz <dingzhong110@gmail.com>
#

include $(TOPDIR)/rules.mk

LUCI_TITLE := LuCI Support for easymesh
LUCI_DEPENDS_BASE := +kmod-cfg80211 +batctl-full +kmod-batman-adv +dawn +luci-proto-batman-adv
PKG_VERSION := 2.0

ifeq ($(CONFIG_PACKAGE_wpad-openssl),y)
	LUCI_DEPENDS := $(LUCI_DEPENDS_BASE) +wpad-openssl
	WPAD_PACKAGE := wpad-openssl
else ifeq ($(CONFIG_PACKAGE_wpad-wolfssl),y)
	LUCI_DEPENDS := $(LUCI_DEPENDS_BASE) +wpad-wolfssl
	WPAD_PACKAGE := wpad-wolfssl
else ifeq ($(CONFIG_PACKAGE_wpad-mbedtls),y)
	LUCI_DEPENDS := $(LUCI_DEPENDS_BASE) +wpad-mbedtls
	WPAD_PACKAGE := wpad-mbedtls
else
$(error "Please select a WPAD package.")
endif

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
