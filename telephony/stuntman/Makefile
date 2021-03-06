# $OpenBSD: Makefile,v 1.22 2018/10/24 14:28:11 sthen Exp $

COMMENT =	STUN server implementing RFCs 5389, 5769, and 5780
NOT_FOR_ARCHS = arm hppa # atomic ops

VERSION =	1.2.13
DISTNAME =	stunserver-${VERSION}
PKGNAME =	stuntman-${VERSION}
CATEGORIES =	telephony net
EXTRACT_SUFX =	.tgz
REVISION =	3

MAINTAINER =	Roman Kravchuk <kravchuk.kp@gmail.com>

HOMEPAGE =	http://www.stunprotocol.org/

MASTER_SITES =	${HOMEPAGE}

# Apache 2.0 license
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB +=	c crypto m pthread ${COMPILER_LIBCXX}

COMPILER =		base-clang ports-gcc base-gcc

BUILD_DEPENDS =	devel/boost

MAKE_FLAGS =	BOOST_INCLUDE='-I${LOCALBASE}/include' \
		FLAVOR_FLAGS='${CXXFLAGS} -Wno-unknown-pragmas -DHAVE_ARC4RANDOM' \
		CXX="${CXX}"

USE_GMAKE =	Yes

WRKDIST =	${WRKDIR}/stunserver

do-install:
	cd ${WRKSRC}; ${INSTALL_PROGRAM} stunserver stunclient ${PREFIX}/sbin
	cd ${WRKSRC}/resources/; ${INSTALL_MAN} stunclient.1 stunserver.1 \
	    ${PREFIX}/man/man1

do-test:
	${WRKSRC}/stuntestcode

.include <bsd.port.mk>
