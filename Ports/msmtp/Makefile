BuildRequires += $(BinDir)/pkg-config # pkg-config
BuildRequires += $(LibDir)/libintl.la # static-gettext
BuildRequires += $(LibDir)/libidn.la # static-libidn

include ../../Library/GNU.mk

Title=		msmtp
Name=		msmtp
Version=	1.4.31
Site=		http://msmtp.sourceforge.net/
Source=		http://sourceforge.net/projects/msmtp/files/msmtp/$(Version)/$(Name)-$(Version).tar.bz2
License=	GPL


ifeq ($(RUDIX_BUILD_WITH_STATIC_LIBS),yes)
LdFlags += -framework CoreFoundation -liconv
endif

EnvExtra += PKG_CONFIG_PATH=/usr/lib/pkgconfig
GnuConfigureExtra += --with-ssl=openssl

define after_install_hook
install -m 644 $(SourceDir)/doc/msmtp* $(InstallDir)/$(DocDir)/$(Name)  
endef

define test_hook
$(BinDir)/msmtp --version
endef
