# $OpenBSD: Makefile,v 1.4 2017/01/03 19:24:43 landry Exp $

COMMENT =		simple DNS resolver for asyncio

MODPY_EGG_VERSION =	1.1.1
DISTNAME =		aiodns-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		net
REVISION =		0

MAINTAINER =		Daniel Jakots <obsd@chown.me>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

FLAVORS =		python3
FLAVOR ?=

RUN_DEPENDS =		net/py-cares${MODPY_FLAVOR}
.if !${FLAVOR:Mpython3}
RUN_DEPENDS += devel/py-trollius
.endif

TEST_DEPENDS =		${RUN_DEPENDS}

do-test:
	@cd ${WRKSRC} && ${MODPY_BIN} -m unittest discover

.include <bsd.port.mk>
