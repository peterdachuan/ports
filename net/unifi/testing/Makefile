# $OpenBSD: Makefile,v 1.6 2018/10/04 17:29:35 sthen Exp $

V=		5.9.29
SNAPPY_V=	1.1.4

# for stable-candidate versions
#BUILD_V=	-04b5d20997

.if 0 && !defined(BUILD_V)
FETCH_MANUALLY+= ""
FETCH_MANUALLY+= "If you have access to UniFi betas, open the beta blog post for $V"
FETCH_MANUALLY+= "and note the suffix from the directory name of the download URLs."
FETCH_MANUALLY+= "Then re-run make, passing it as BUILD_V. For example with a path"
FETCH_MANUALLY+= "with 1.0.0-xxxxxxxxxx, run 'make BUILD_V=-xxxxxxxxxx'."
FETCH_MANUALLY+= ""
.endif

.include <bsd.port.mk>
