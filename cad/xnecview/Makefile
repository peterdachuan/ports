# $OpenBSD: Makefile,v 1.25 2017/11/21 00:12:59 naddy Exp $

COMMENT=	NEC2 antenna simulator visualizer

DISTNAME=	xnecview-1.36
REVISION=	1
EXTRACT_SUFX=	.tgz

MASTER_SITES=	http://wwwhome.cs.utwente.nl/~ptdeboer/ham/xnecview/

CATEGORIES=	cad hamradio

HOMEPAGE=	http://www.cs.utwente.nl/~ptdeboer/ham/xnecview/

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB =  X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama Xrandr
WANTLIB += Xrender atk-1.0 c cairo fontconfig freetype gdk-x11-2.0
WANTLIB += gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0 gtk-x11-2.0 iconv
WANTLIB += intl m pango-1.0 pangocairo-1.0 pangoft2-1.0 png pthread z

LIB_DEPENDS =		x11/gtk+2

USE_GMAKE =	Yes
MAKE_FLAGS =	CC="${CC}" LD="${LD}" myCFLAGS="${CFLAGS}"

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/xnecview ${PREFIX}/bin/
	${INSTALL_MAN} ${WRKSRC}/xnecview.1x ${PREFIX}/man/man1/xnecview.1

.include <bsd.port.mk>
