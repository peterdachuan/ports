# $OpenBSD: Makefile,v 1.8 2018/10/22 20:30:41 rsadowski Exp $

COMMENT =	central daemon of KDE workspaces
DISTNAME =	kded-${VERSION}

SHARED_LIBS =	kdeinit5_kded5		4.2

WANTLIB += ${COMPILER_LIBCXX} KF5ConfigCore KF5CoreAddons KF5Crash
WANTLIB += KF5DBusAddons KF5Service Qt5Core Qt5DBus Qt5Gui Qt5Widgets
WANTLIB += c m

BUILD_DEPENDS =	devel/kf5/kdoctools \
		devel/kf5/kinit

RUN_DEPENDS =	devel/kf5/kdoctools \
		devel/kf5/kinit

LIB_DEPENDS =	devel/kf5/kconfig \
		devel/kf5/kcoreaddons \
		devel/kf5/kcrash \
		devel/kf5/kdbusaddons \
		devel/kf5/kservice

.include <bsd.port.mk>
