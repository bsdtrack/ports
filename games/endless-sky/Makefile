COMMENT =	space exploration and combat game similar to Escape Velocity
CATEGORIES =	games x11

GH_ACCOUNT =	endless-sky
GH_PROJECT =	endless-sky
GH_TAGNAME =	v0.10.12

HOMEPAGE =	https://endless-sky.github.io/
MAINTAINER =	Brian Callahan <bcallah@openbsd.org>

# Game: GPLv3+
# Assets: Combination of CC-BY-SA 4.0, 3.0, and Public Domain
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL GLEW SDL2 c jpeg m mad openal
WANTLIB += png uuid z

# C++11
COMPILER =	base-clang ports-gcc

MODULES =	devel/cmake

BUILD_DEPENDS =	devel/catch2 \
		devel/ninja

LIB_DEPENDS =	audio/libmad \
		audio/openal \
		devel/sdl2 \
		graphics/glew \
		graphics/jpeg \
		graphics/png \
		sysutils/e2fsprogs

RUN_DEPENDS =	devel/desktop-file-utils \
		x11/gtk+4,-guic

MAKE_ENV =	CXXFLAGS="${CXXFLAGS} -I${LOCALBASE}/include -I${X11BASE}/include" \
		LDFLAGS="${LDFLAGS} -L${LOCALBASE}/lib -L${X11BASE}/lib"

NO_TEST =	Yes

pre-configure:
	sed -i 's,/usr/local,${LOCALBASE},g' ${WRKSRC}/source/Files.cpp

# Don't bother with CMake, install the manual page ourselves.
post-install:
	${INSTALL_MAN} ${WRKSRC}/endless-sky.6 ${PREFIX}/man/man6

.include <bsd.port.mk>
