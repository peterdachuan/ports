# $OpenBSD: Makefile,v 1.26 2018/08/12 22:57:21 jca Exp $

COMMENT=	trivial database library

# Keep in sync with the version bundled in net/samba
DISTNAME=	tdb-1.3.16

SHARED_LIBS+=	tdb	4.3

CATEGORIES=	databases

HOMEPAGE=	https://tdb.samba.org/

MAINTAINER=	Jeremie Courreges-Anglas <jca@wxcvbn.org>

# LGPLv3+
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c m pthread util ${MODPY_WANTLIB}

MASTER_SITES=	https://download.samba.org/pub/tdb/

MODULES=	lang/python
MODPY_RUNDEP=	No
MODPY_ADJ_FILES= buildtools/bin/waf

BUILD_DEPENDS=	textproc/docbook-xsl \
		textproc/libxslt

LIB_DEPENDS=	${MODPY_LIB_DEPENDS}

WAF_ARGS=	-v -j ${MAKE_JOBS}
MAKE_FLAGS=	WAF_ARGS="${WAF_ARGS}"
.for _l _v in ${SHARED_LIBS}
MAKE_ENV +=	LIB${_l:S/-/_/g}_VERSION=${_v}
.endfor
TEST_ENV=	LD_LIBRARY_PATH="${WRKSRC}/bin/default"

CONFIGURE_STYLE= simple
CONFIGURE_ARGS= --mandir="${PREFIX}/man" \
		--disable-rpath

.include <bsd.port.mk>
