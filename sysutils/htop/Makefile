# $OpenBSD: Makefile,v 1.12 2018/09/12 23:00:55 ians Exp $

COMMENT =	interactive process viewer

V =		2.2.0
DISTNAME =	htop-${V}
REVISION =	7

CATEGORIES =	sysutils

HOMEPAGE =	https://hisham.hm/htop/index.php

MAINTAINER =	Ian Sutton <ian@ce.gl>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =	c curses kvm m

MASTER_SITES =	https://hisham.hm/htop/releases/${V}/

MODULES =	lang/python
RUN_DEPENDS =	devel/desktop-file-utils

NO_TEST =	Yes

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS +=	--disable-unicode \
			--disable-taskstats

MODPY_RUNDEP =		No
MODPY_ADJ_FILES =	scripts/MakeHeader.py

# htop has some bugs which take hours or days to reach.
# Keep the symbols to give a chance to the user to get an useful coredump.
MAKE_FLAGS =	AM_CPPFLAGS="-DDEBUG"
DEBUG =		-g

.include <bsd.port.mk>
