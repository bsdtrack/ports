COMMENT =	color correction utility for digital images
DISTNAME =	delaboratory-0.8
CATEGORIES =	graphics x11
REVISION =	7

# GPLv3+
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} c iconv lzma m tiff wx_baseu-3.2
WANTLIB += wx_baseu_net-3.2 wx_baseu_xml-3.2
WANTLIB += wx_gtk3u_core-3.2 wx_gtk3u_html-3.2 wx_gtk3u_qa-3.2
WANTLIB += wx_gtk3u_xrc-3.2 xml2 z

COMPILER =		base-clang ports-gcc base-gcc

SITES =		https://distfiles.sigtrap.nl/

LIB_DEPENDS =	converters/libiconv \
		textproc/libxml \
		x11/wxWidgets,-main>=3.0.4

RUN_DEPENDS =	graphics/dcraw

USE_GMAKE =	Yes
MAKE_FLAGS =	CXX="${CXX}" OPTFLAGS="${CXXFLAGS}"

NO_TEST =	Yes

# prevent confusion with system <semaphore.h>
post-patch:
	mv ${WRKSRC}/gui_wx/semaphore.h ${WRKSRC}/gui_wx/desemaphore.h

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/delaboratory ${PREFIX}/bin

.include <bsd.port.mk>
