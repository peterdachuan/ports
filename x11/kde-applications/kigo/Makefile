# $OpenBSD: Makefile,v 1.1.1.1 2018/11/16 07:08:14 rsadowski Exp $

COMMENT =	Go board game
DISTNAME =	kigo-${VERSION}
CATEGORIES =	games

HOMEPAGE =	https://www.kde.org/applications/games/kigo

KDE5 =		Yes

WANTLIB += ${COMPILER_LIBCXX} KF5Attica KF5Auth KF5Codecs KF5Completion
WANTLIB += KF5ConfigCore KF5ConfigGui KF5ConfigWidgets KF5CoreAddons
WANTLIB += KF5Crash KF5DBusAddons KF5I18n KF5JobWidgets KF5KDEGames
WANTLIB += KF5KDEGamesPrivate KF5KIOCore KF5KIOWidgets KF5NewStuff
WANTLIB += KF5NewStuffCore KF5Service KF5SonnetUi KF5TextWidgets
WANTLIB += KF5WidgetsAddons KF5XmlGui Qt5Concurrent Qt5Core Qt5DBus
WANTLIB += Qt5Gui Qt5Network Qt5Qml Qt5Quick Qt5QuickWidgets Qt5Svg
WANTLIB += Qt5Widgets Qt5Xml c m

BUILD_DEPENDS +=devel/gettext-tools \
		devel/kf5/kdoctools \
		devel/kf5/kcrash \
		x11/qt5/qtquickcontrols \
		x11/qt5/qtdeclarative

RUN_DEPENDS =	devel/kf5/kdoctools \
		devel/kf5/kcrash \
		devel/desktop-file-utils \
		games/gnugo \
		x11/gtk+3,-guic \
		x11/qt5/qtquickcontrols \
		x11/qt5/qtdeclarative

LIB_DEPENDS =	devel/kf5/kauth \
		devel/kf5/kcodecs \
		devel/kf5/ki18n \
		devel/kf5/kcrash \
		devel/kf5/kdbusaddons \
		devel/kf5/kconfig \
		devel/kf5/kcoreaddons \
		devel/kf5/kxmlgui \
		devel/kf5/knewstuff \
		devel/kf5/kconfigwidgets \
		devel/kf5/kio \
		x11/qt5/qtsvg \
		x11/kde-applications/libkdegames

.include <bsd.port.mk>
