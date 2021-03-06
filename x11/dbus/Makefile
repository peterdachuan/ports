# $OpenBSD: Makefile,v 1.156 2018/09/04 12:46:27 espie Exp $

PORTROACH=		limitw:1,even
DPB_PROPERTIES=		parallel

COMMENT-main=		message bus system
COMMENT-suid=		DBus setuid helper for starting system services

V=			1.12.10
DISTNAME=		dbus-${V}
EPOCH-main=		0

PKGNAME-main=		${DISTNAME}
PKGNAME-suid=		dbus-daemon-launch-helper-${V}
REVISION-main=		0

SHARED_LIBS +=  dbus-1               11.2     # 22.8

CATEGORIES=		x11

HOMEPAGE=		http://dbus.freedesktop.org/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c expat pthread

WANTLIB-main += ${WANTLIB} ICE SM X11 xcb

WANTLIB-suid +=	${WANTLIB} dbus-1

MULTI_PACKAGES=		-main -suid

MASTER_SITES=		http://dbus.freedesktop.org/releases/dbus/

USE_GMAKE=		Yes

BUILD_DEPENDS=		textproc/xmlto

LIB_DEPENDS-suid=	${BASE_PKGPATH},-main

AUTOCONF_VERSION=	2.69
CONFIGURE_STYLE=	autoconf
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"
CONFIGURE_ARGS=		--with-dbus-user=_dbus \
			--disable-doxygen-docs \
			--disable-ducktype-docs \
			--disable-modular-tests \
			--disable-systemd

# autolaunch brings too much magic to spawn a dbus-daemon(1) process and we want
# predictable buses; don't disable it yet because it breaks applications that
# require a user session and can't handle the lack of one (e.g. net/gpodder)
#CONFIGURE_ARGS +=	--disable-x11-autolaunch

# we can't use --without-x because this would break bus activated clients (since
# we don't use systemd)
#CONFIGURE_ARGS +=	--without-x

# gives no chance of picking up devel/libexecinfo
CONFIGURE_ENV +=	ac_cv_header_execinfo_h=no \
			ac_cv_func_backtrace=no

# Full test coverage is disabled:
# * changes the final dbus binaries
# * requires py-gobject and dbus-python (dependency loop)
# * requires the python MODULE
#MODULES +=		lang/python
#TEST_DEPENDS +=	devel/py-gobject3
#BUILD_DEPENDS +=	devel/py-gobject3
#CONFIGURE_ARGS+=	--enable-developer
#CONFIGURE_ARGS+=	--enable-modular-tests
#CONFIGURE_ARGS+=	--enable-tests
#CONFIGURE_ARGS+=	--enable-verbose-mode

FAKE_FLAGS=		sysconfdir=${TRUEPREFIX}/share/examples/dbus

post-install:
	rm -r ${WRKINST}/var/{lib,run/dbus}

.include <bsd.port.mk>
