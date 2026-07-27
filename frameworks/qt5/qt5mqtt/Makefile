include $(TOPDIR)/rules.mk

PKG_NAME:=qt5mqtt
PKG_VERSION:=5.15.16
PKG_RELEASE:=1
PKG_HASH:=4956c72c555ff985ed6d77fed71d5374116ce106c591e0db94046332e9e32536

PKG_SYS_NAME:=qtmqtt-everywhere-src-$(PKG_VERSION)
PKG_SOURCE:=qtmqtt-everywhere-opensource-src-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://download.qt.io/archive/qt/$(basename $(PKG_VERSION))/$(PKG_VERSION)/submodules

PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_SYS_NAME)
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=qt5tools/host

include ../common.mk
include $(INCLUDE_DIR)/package.mk
include ../qmake.mk

define Package/qt5mqtt
  SECTION:=video-frameworks
  CATEGORY:=Video
  SUBMENU:=Frameworks and Toolkits
  TITLE:=qt5mqtt
  DEPENDS:=+qt5base-core +qt5base-network +libstdcpp +libudev
endef

define Build/InstallDev
	$(call Build/Install/HostFiles,$(1))
	$(call Build/Install/Headers,$(1))
	$(call Build/Install/Libs,$(1),*)
endef

define Package/qt5mqtt/install
	$(call Build/Install/Libs,$(1),libQt5Mqtt)
endef

$(eval $(call BuildPackage,qt5mqtt))
