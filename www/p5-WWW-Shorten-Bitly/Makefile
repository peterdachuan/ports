# $OpenBSD: Makefile,v 1.5 2017/06/02 07:41:47 benoit Exp $

COMMENT =		interface to bit.ly shortening site

DISTNAME =		WWW-Shorten-Bitly-2.001
CATEGORIES =		www

# Perl
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
PKG_ARCH =		*

BUILD_DEPENDS = 	${RUN_DEPENDS}
RUN_DEPENDS =		converters/p5-JSON-MaybeXS \
			www/p5-WWW-Shorten \
			devel/p5-Path-Tiny \
			devel/p5-File-HomeDir \
			www/p5-LWP-Protocol-https

.include <bsd.port.mk>
