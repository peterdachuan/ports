# $OpenBSD: Makefile,v 1.4 2017/06/12 10:57:57 ajacoutot Exp $

COMMENT =	py.test xdist plugin for distributed testing

DISTNAME =		pytest-xdist-${MODPY_EGG_VERSION}
MODPY_EGG_VERSION =	1.16.0
MODPY_PI =		Yes
PKGNAME =		py-test-xdist-${MODPY_EGG_VERSION}
REVISION =		0

CATEGORIES =	devel

HOMEPAGE =	https://github.com/pytest-dev/pytest-xdist

# MIT
PERMIT_PACKAGE_CDROM =	Yes

FLAVORS =		python3
FLAVOR ?=

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
BUILD_DEPENDS +=	devel/py-setuptools_scm${MODPY_FLAVOR}
RUN_DEPENDS =		devel/py-execnet${MODPY_FLAVOR} \
			devel/py-test${MODPY_FLAVOR} \
			devel/py-apipkg${MODPY_FLAVOR}
TEST_DEPENDS =		${RUN_DEPENDS} \
			${FULLPKGNAME}:${FULLPKGPATH}

do-test:
	cd ${WRKSRC} && ${MODPY_BIN} -m pytest testing

.include <bsd.port.mk>
