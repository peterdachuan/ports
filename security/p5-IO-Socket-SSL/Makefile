# $OpenBSD: Makefile,v 1.120 2018/09/17 14:14:29 bluhm Exp $

COMMENT =	Perl SSL sockets with IO::Socket interface

DISTNAME =	IO-Socket-SSL-2.060

CATEGORIES =	security

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# perl
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
RUN_DEPENDS =		security/p5-Net_SSLeay>=1.83
TEST_DEPENDS =		net/p5-IO-Socket-INET6>=2.62 \
			converters/p5-Net-IDN-Encode \
			www/p5-URI>=1.50

PKG_ARCH =		*

MODCPAN_EXAMPLES =	Yes
MODCPAN_EXAMPLES_DIST =	example

.include <bsd.port.mk>
