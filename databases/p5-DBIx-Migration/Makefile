# $OpenBSD: Makefile,v 1.12 2016/03/20 19:56:11 naddy Exp $

COMMENT =	seamless DB up- and downgrades

MODULES =	cpan
PKG_ARCH =	*
DISTNAME =	DBIx-Migration-0.07
CATEGORIES =	databases

# perl
PERMIT_PACKAGE_CDROM =	Yes

CONFIGURE_STYLE=modbuild

BUILD_DEPENDS =	${RUN_DEPENDS}
RUN_DEPENDS =	devel/p5-Class-Accessor \
		devel/p5-File-Slurp \
		databases/p5-DBD-SQLite

MAKE_ENV +=	TEST_POD=1

.include <bsd.port.mk>
