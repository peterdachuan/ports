# $OpenBSD: Makefile,v 1.14 2018/06/01 15:44:28 sthen Exp $

COMMENT=	system statistics gathering library

DISTNAME=	libstatgrab-0.91
REVISION=	3
CATEGORIES=	sysutils

HOMEPAGE=	http://www.i-scream.org/libstatgrab/

SHARED_LIBS +=  statgrab             1.0      # 10.0

# LGPLv2.1/GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c ncurses m pthread

MASTER_SITES=	http://ftp.i-scream.org/pub/i-scream/libstatgrab/ \
		fhttp://ftp.uk.i-scream.org/pub/i-scream/libstatgrab/

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS+=--disable-setgid-binaries \
		--disable-setuid-binaries \
		--disable-deprecated

.include <bsd.port.mk>
