COMMENT =	general purpose flash card program for KDE
DISTNAME =	kwordquiz-${VERSION}
CATEGORIES =	games

HOMEPAGE =	https://www.kde.org/applications/games/kwordquiz

WANTLIB += ${COMPILER_LIBCXX} KEduVocDocument KF5Attica KF5ConfigCore
WANTLIB += KF5ConfigGui KF5CoreAddons KF5Crash KF5DBusAddons KF5I18n
WANTLIB += KF5NewStuffCore KF5Notifications KF5NotifyConfig Qt5Core
WANTLIB += Qt5DBus Qt5Gui Qt5Multimedia Qt5Network Qt5PrintSupport
WANTLIB += Qt5Qml Qt5QmlModels Qt5Quick Qt5QuickControls2 Qt5Svg
WANTLIB += Qt5Widgets Qt5Xml c m

MODKDE5_ICON_CACHE = yes
MODKDE5_TRANSLATIONS = yes
MODKF5_I18N_CONFLICT = yes
MODKF5_L10N_CONFLICT = yes
MODKDE5_DESKTOP_FILE = yes
MODKDE5_DOCS = yes

BUILD_DEPENDS =	graphics/kirigami-addons

RUN_DEPENDS =	graphics/kirigami-addons

LIB_DEPENDS =	devel/kf5/attica \
		devel/kf5/kconfig \
		devel/kf5/kcoreaddons \
		devel/kf5/kcrash \
		devel/kf5/ki18n \
		devel/kf5/knewstuff \
		devel/kf5/knotifications \
		devel/kf5/knotifyconfig \
		x11/kde-applications/libkeduvocdocument>=${MODKDE_VERSION} \
		x11/qt5/qtmultimedia \
		x11/qt5/qtquickcontrols2 \
		x11/qt5/qtsvg
.include <bsd.port.mk>
