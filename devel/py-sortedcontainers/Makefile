# $OpenBSD: Makefile,v 1.1.1.1 2017/12/03 10:27:33 rpointel Exp $

COMMENT =	Python Sorted Container Types

MODPY_EGG_VERSION =	1.5.7
DISTNAME =	sortedcontainers-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}

CATEGORIES =	devel

HOMEPAGE =	http://www.grantjenks.com/docs/sortedcontainers/

# Apache v2
PERMIT_PACKAGE_CDROM =	Yes

MODULES =	lang/python
MODPY_PI =	Yes

FLAVORS =	python3
FLAVOR ?=

MODPY_SETUPTOOLS = Yes

TEST_DEPENDS =	devel/py-nose${MODPY_FLAVOR}

do-test:
	cd ${WRKSRC} && nosetests${MODPY_BIN_SUFFIX}

.include <bsd.port.mk>
