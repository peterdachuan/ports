# $OpenBSD: Makefile,v 1.60 2018/07/06 06:04:45 espie Exp $

COMMENT=		mouse accessibility enhancements for GNOME

GNOME_PROJECT=		mousetweaks
GNOME_VERSION=		3.12.0
REVISION=		3

# GPLv3 - GFDLv1.3
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += X11 Xcursor Xfixes Xtst atk-1.0 c cairo cairo-gobject
WANTLIB += gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0
WANTLIB += gobject-2.0 gtk-3 pango-1.0 pangocairo-1.0
WANTLIB += pthread intl

MODULES=		devel/dconf \
			x11/gnome

BUILD_DEPENDS=		devel/gsettings-desktop-schemas
RUN_DEPENDS=		devel/gsettings-desktop-schemas
LIB_DEPENDS=		x11/gtk+3

MODGNOME_TOOLS=		yelp

CONFIGURE_STYLE=	gnu

# glib-mkenums(1), UnicodeEncodeError:
# 'ascii' codec can't encode character u'\xa9' in position 16: ordinal not in range(128)
MAKE_ENV=		PYTHONIOENCODING=utf8

.include <bsd.port.mk>
