# $OpenBSD: Makefile,v 1.45 2018/11/14 20:48:21 sthen Exp $

COMMENT=	virtual machine designed for interpreted languages

V=		7.10.0
DISTNAME=	parrot-$V
REVISION=	6
CATEGORIES=	lang perl6
SHARED_LIBS=	parrot	11.0

HOMEPAGE=	http://www.parrot.org/

MASTER_SITES=	http://ftp.parrot.org/releases/all/$V/ \
		ftp://ftp.parrot.org/pub/parrot/releases/all/$V/

# Artistic2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += GL GLU c glut gmp iconv icudata icuuc intl m ncurses pthread
WANTLIB += readline ${COMPILER_LIBCXX} util z ffi

COMPILER =		base-clang ports-gcc base-gcc

BUILD_DEPENDS=		graphics/glew \
			devel/pcre
LIB_DEPENDS=		textproc/icu4c \
			devel/gettext \
			devel/gmp \
			graphics/freeglut \
			devel/libffi
TEST_DEPENDS=		devel/p5-TAP-Harness-Multiple \
			devel/p5-Test-Perl-Critic

CONFIGURE_SCRIPT=	/usr/bin/perl Configure.pl
CONFIGURE_STYLE=	simple
CONFIGURE_ARGS+= \
	--prefix="${PREFIX}" \
	--cc="${CC}" \
	--ccflags="-I${LOCALBASE}/include -I${X11BASE}/include -pthread" \
	--optimize="${CFLAGS}" \
	--link="${CXX}" \
	--linkflags="-L${LOCALBASE}/lib -L${X11BASE}/lib -pthread" \
	--ld="${CXX}" \
	--ldflags="-L${LOCALBASE}/lib -L${X11BASE}/lib" \
	--make="${MAKE_PROGRAM}" \
	--parrot_is_shared \
	--icu-config="${LOCALBASE}/bin/icu-config"

CONFIGURE_ENV =		LIBparrot_VERSION=${LIBparrot_VERSION}

MAKE_ENV=		LIBparrot_VERSION=${LIBparrot_VERSION}

ALL_TARGET =		all docs
INSTALL_TARGET =	install install-doc
TEST_TARGET=		fulltest

SUBST_VARS +=		V

pre-configure:
	${SUBST_CMD} ${WRKSRC}/config/init/hints/openbsd.pm

post-install:
	${INSTALL_DATA} ${WRKSRC}/blib/lib/libparrot.so.${LIBparrot_VERSION} \
		${PREFIX}/lib

.include <bsd.port.mk>
