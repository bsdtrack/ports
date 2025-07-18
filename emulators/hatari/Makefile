ONLY_FOR_ARCHS = i386 amd64 powerpc powerpc64 arm

COMMENT =	Atari ST/STE/TT/Falcon emulator

DISTNAME =	hatari-2.6.0
EXTRACT_SUFX =	.tar.bz2

CATEGORIES =	emulators

HOMEPAGE =	https://www.hatari-emu.org/

MAINTAINER =	Frederic Cambus <fcambus@openbsd.org>

# GPLv2+
PERMIT_PACKAGE =	Yes

WANTLIB += ICE SDL2 SM X11 Xext c capstone m png portmidi readline
WANTLIB += z

SITES =		https://framagit.org/hatari/releases/-/raw/main/v2.6/

RUN_DEPENDS =	devel/desktop-file-utils \
		misc/shared-mime-info \
		sysutils/mtools \
		x11/gtk+4,-guic

LIB_DEPENDS =	audio/portmidi \
		devel/capstone/main \
		devel/sdl2 \
		graphics/png

MODULES =	devel/cmake \
		lang/python

MODPY_ADJ_FILES = tools/debugger/*.py \
		  tools/hconsole/*.py \
		  tools/*.py

CONFIGURE_ARGS = -DMANDIR=${PREFIX}/man/man1

NO_TEST =	Yes

pre-configure:
	@sed -i 's,/usr/share,${PREFIX}/share,' \
		${WRKSRC}/tools/hconsole/hconsole.1

post-install:
	${MODPY_COMPILEALL} ${PREFIX}/share/hatari/hconsole/
	gunzip ${PREFIX}/man/man1/*.1.gz

.include <bsd.port.mk>
