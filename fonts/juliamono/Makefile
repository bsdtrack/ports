COMMENT =	typeface carefully crafted & designed for computer screens

V =		0.060
DISTNAME =	JuliaMono
PKGNAME =	juliamono-$V

CATEGORIES =	fonts

HOMEPAGE =	https://juliamono.netlify.app/

MAINTAINER =    Justin Berthault <justin.berthault@zaclys.net>

# SIL OFL 1.1
PERMIT_PACKAGE =	Yes

SITES =		https://github.com/cormullion/juliamono/releases/download/v${V}/
DISTFILES =     ${DISTNAME}-${V}{${DISTNAME}}${EXTRACT_SUFX}

NO_BUILD =	Yes
NO_TEST =	Yes

WRKDIST =	${WRKDIR}

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/fonts/juliamono
	${INSTALL_DATA} ${WRKSRC}/*.ttf ${PREFIX}/share/fonts/juliamono
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/juliamono
	${INSTALL_DATA} ${WRKSRC}/LICENSE ${PREFIX}/share/doc/juliamono

.include <bsd.port.mk>
