# $OpenBSD: Makefile,v 1.8 2018/10/22 20:30:43 rsadowski Exp $

COMMENT =		KDE framework for managing menu and toolbar actions
DISTNAME =		kxmlgui-${VERSION}

SHARED_LIBS =		KF5XmlGui		4.2

WANTLIB += ${COMPILER_LIBCXX} KF5Attica KF5Auth KF5Codecs KF5ConfigCore
WANTLIB += KF5ConfigGui KF5ConfigWidgets KF5CoreAddons KF5GlobalAccel
WANTLIB += KF5I18n KF5IconThemes KF5ItemViews KF5SonnetUi KF5TextWidgets
WANTLIB += KF5WidgetsAddons KF5WindowSystem Qt5Core Qt5DBus Qt5Gui
WANTLIB += Qt5Network Qt5PrintSupport Qt5Widgets Qt5Xml c m

MODULES =		lang/python

BUILD_DEPENDS =		devel/gettext-tools

LIB_DEPENDS =		devel/kf5/attica \
			devel/kf5/kconfig \
			devel/kf5/kconfigwidgets \
			devel/kf5/kcoreaddons \
			devel/kf5/kglobalaccel \
			devel/kf5/ki18n \
			devel/kf5/kiconthemes \
			devel/kf5/kitemviews \
			devel/kf5/ktextwidgets \
			devel/kf5/kwidgetsaddons \
			devel/kf5/kwindowsystem

TEST_IS_INTERACTIVE =	X11
PORTHOME =		${WRKDIR}

# TODO: The following tests FAILED:
# 5 - kxmlgui_unittest (Failed)

.include <bsd.port.mk>
