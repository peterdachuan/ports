# $OpenBSD: Makefile,v 1.2 2018/11/02 18:48:39 naddy Exp $

COMMENT=	COBOL compiler, formerly known as OpenCOBOL

DISTNAME =	gnucobol-2.2
REVISION =	0

SHARED_LIBS +=	cob	4.0	# 4.0

CATEGORIES =	lang

HOMEPAGE =	http://www.opencobol.org/

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# compiler: GPLv3+
# run-time library: LGPLv3+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c curses db gmp iconv intl m

MASTER_SITES =	${MASTER_SITE_GNU:=gnucobol/}

LIB_DEPENDS =	databases/db/v4 \
		devel/gettext \
		devel/gmp

CONFIGURE_STYLE = gnu

CONFIGURE_ENV =	LDFLAGS="${LDFLAGS} -L${LOCALBASE}/lib" \
		CFLAGS="${CFLAGS} -I${LOCALBASE}/include" \
		CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include -I${LOCALBASE}/include/db4"

.include <bsd.port.mk>
