# $OpenBSD: Makefile,v 1.21 2018/09/04 12:46:20 espie Exp $

COMMENT=		802.11 WEP and WPA-PSK keys cracking program
DISTNAME=		aircrack-ng-1.1
REVISION=		15
CATEGORIES=		security

HOMEPAGE=		http://www.aircrack-ng.org/

MAINTAINER=		Benoit Lecocq <benoit@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=   Yes

WANTLIB=		c pthread crypto ssl z

MASTER_SITES=		http://download.aircrack-ng.org/

WANTLIB +=		sqlite3
LIB_DEPENDS=		databases/sqlite3

USE_GMAKE=		Yes
MAKE_ENV+=		SQLITE=true UNSTABLE=true
MAKE_FLAGS+=		CC=${CC}

NO_TEST=		Yes

post-extract:
	perl -i -pe 's/\r\n/\n/' ${WRKSRC}/src/osdep/byteorder.h

pre-configure:
	${SUBST_CMD} ${WRKSRC}/src/airodump-ng.h

.include <bsd.port.mk>
