# $OpenBSD: Makefile,v 1.29 2018/01/11 19:27:12 rpe Exp $

COMMENT =		lightweight HTTP/SSL proxy

V =			1.8.4
DISTNAME =		tinyproxy-$V
CATEGORIES =		www net
REVISION =		0

HOMEPAGE =		https://www.banu.com/tinyproxy/
MAINTAINER =		frantisek holop <minusf@obiit.org>

# GPLv2+
PERMIT_PACKAGE_CDROM =		Yes

BUILD_DEPENDS =		textproc/asciidoc>=8.6.8

SEPARATE_BUILD =	Yes
CONFIGURE_STYLE =	gnu

WANTLIB =		c

MASTER_SITES =		https://github.com/tinyproxy/tinyproxy/releases/download/$V/

SYSCONFDIR =		${BASESYSCONFDIR}/tinyproxy

post-install:
	mv ${WRKINST}${SYSCONFDIR} ${PREFIX}/share/examples

.include <bsd.port.mk>
