# $OpenBSD: Makefile,v 1.1.1.1 2018/04/04 21:57:58 fcambus Exp $

COMMENT =	fast, compact, powerful binary deserialization

DISTNAME =	Sereal-Decoder-4.005

CATEGORIES =	converters

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# Perl, BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =	c perl zstd

MODULES =	cpan

BUILD_DEPENDS =	devel/p5-Devel-CheckLib

LIB_DEPENDS =	archivers/zstd

TEST_DEPENDS =	converters/p5-Sereal-Encoder>=4.002 \
		devel/p5-Test-Deep \
		devel/p5-Test-Differences \
		devel/p5-Test-LongString \
		devel/p5-Test-Warn

CPAN_AUTHOR =	YVES

post-extract:
	rm -r -- ${WRKSRC}/inc/Devel ${WRKSRC}/zstd

pre-configure:
	${SUBST_CMD} ${WRKSRC}/Makefile.PL

.include <bsd.port.mk>
