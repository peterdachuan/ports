# $OpenBSD: Makefile,v 1.19 2015/10/31 16:54:10 sthen Exp $

COMMENT=		RCS parsing library for Python

GH_ACCOUNT=		corecode
GH_PROJECT=		rcsparse
GH_COMMIT=		206bca0b90f5780815c0b6c6cbccfd03f27f6985

DISTNAME=		rcsparse-20151027
PKGNAME=		py-${DISTNAME}

CATEGORIES=     	devel

# AGPLv3+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB +=		${MODPY_WANTLIB} pthread

MODULES=		lang/python
NO_TEST=		Yes

.include <bsd.port.mk>
