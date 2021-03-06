# $OpenBSD: Makefile,v 1.25 2017/10/23 17:11:05 sthen Exp $

COMMENT=		.NET language binding for the GTK+2 toolkit

MAJOR=			12
MINOR=			45
VERSION=		2.${MAJOR}.${MINOR}

DISTNAME=		gtk-sharp-${VERSION}
PKGNAME=		mono-gtk2-${VERSION}
REVISION=		0

CATEGORIES=		x11

HOMEPAGE=		http://www.mono-project.com/docs/gui/gtksharp/

# LGPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender atk-1.0 cairo expat ffi fontconfig freetype
WANTLIB += gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glade-2.0 glib-2.0
WANTLIB += gmodule-2.0 gobject-2.0 graphite2 gthread-2.0 gtk-x11-2.0
WANTLIB += harfbuzz iconv intl lzma m pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 pcre pixman-1 png pthread
WANTLIB += xcb xcb-render xcb-shm xml2 z

MASTER_SITES=		https://download.mono-project.com/sources/gtk-sharp2${MAJOR}/

USE_GMAKE=		Yes

MODULES=		lang/mono

LIB_DEPENDS=		devel/libglade2 \
			x11/gtk+2

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

DLLMAP_FILES=		atk/atk-sharp.dll.config \
			gdk/gdk-sharp.dll.config \
			glade/glade-sharp.dll.config \
			glib/glib-sharp.dll.config \
			gtk/gtk-sharp.dll.config \
			gtkdotnet/gtk-dotnet.dll.config \
			pango/pango-sharp.dll.config

.include <bsd.port.mk>
