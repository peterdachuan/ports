# $OpenBSD: Makefile,v 1.47 2018/11/10 12:12:49 ajacoutot Exp $

COMMENT=		dynamic pixel format conversion library

V=			0.1.60
DISTNAME=		babl-${V}
EXTRACT_SUFX=		.tar.bz2

API_VERSION=		${V:R}
SUBST_VARS=		API_VERSION

CATEGORIES=		graphics devel

SHARED_LIBS +=  babl-0.1             1.5      # 159.1

HOMEPAGE=		http://gegl.org/babl/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv3/LGPLv3
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += m pthread

MASTER_SITES=		http://download.gimp.org/pub/babl/${V:R}/

USE_GMAKE=		Yes

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		LDFLAGS="-pthread" \
			ac_cv_path_W3M=no \
			ac_cv_path_RSVG=no

CONFIGURE_ARGS +=	--enable-mmx \
			--disable-altivec

.if ${MACHINE_ARCH} == "amd64"
CONFIGURE_ARGS +=	--enable-sse \
			--enable-sse2
.else
CONFIGURE_ARGS +=	--disable-sse \
			--disable-sse2
.endif

post-install:
	rm ${PREFIX}/lib/babl-${API_VERSION}/*.{a,la}

.include <bsd.port.mk>
