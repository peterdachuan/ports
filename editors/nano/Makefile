# $OpenBSD: Makefile,v 1.101 2018/11/17 18:09:02 naddy Exp $

COMMENT=	Pico editor clone with enhancements

DISTNAME=	nano-3.2
CATEGORIES=	editors
HOMEPAGE=	https://www.nano-editor.org/

MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

MASTER_SITES=	https://www.nano-editor.org/dist/v3/ \
		${MASTER_SITE_GNU:=nano/}
PORTROACH=	site:https://www.nano-editor.org/dist/latest/
EXTRACT_SUFX=	.tar.xz

# GPLv3+
PERMIT_PACKAGE_CDROM=	Yes

LIB_DEPENDS=	devel/gettext
WANTLIB=	c curses iconv intl

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--disable-libmagic
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

# configure tests for groff -Thtml, but assumes the existence of groff
pre-configure:
	@ln -s /usr/bin/false ${WRKDIR}/bin/groff

post-install:
	sed -i -e 's:/etc:${SYSCONFDIR}:g;' ${PREFIX}/man/man5/nanorc.5
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/nano
	${INSTALL_DATA} ${WRKBUILD}/doc/sample.nanorc \
	    ${PREFIX}/share/examples/nano

.include <bsd.port.mk>
