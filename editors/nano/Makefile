COMMENT=	simple editor, inspired by Pico

DISTNAME=	nano-8.5
CATEGORIES=	editors
HOMEPAGE=	https://www.nano-editor.org/

MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

SITES=		https://www.nano-editor.org/dist/v8/ \
		${SITE_GNU:=nano/}
PORTROACH=	site:https://www.nano-editor.org/dist/latest/
EXTRACT_SUFX=	.tar.xz

# GPLv3+
PERMIT_PACKAGE=	Yes

LIB_DEPENDS=	devel/gettext,-runtime
WANTLIB=	c curses iconv intl pthread

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--disable-libmagic
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib"

DEBUG_PACKAGES=	${BUILD_PACKAGES}

# configure tests for groff -Thtml, but assumes the existence of groff
pre-configure:
	@ln -s /usr/bin/false ${WRKDIR}/bin/groff

post-install:
	sed -i -e 's:/etc:${SYSCONFDIR}:g' -e 's:/usr:${TRUEPREFIX}:g' \
	    ${PREFIX}/man/man1/nano.1 ${PREFIX}/man/man5/nanorc.5
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/nano
	${INSTALL_DATA} ${WRKBUILD}/doc/sample.nanorc \
	    ${PREFIX}/share/examples/nano

.include <bsd.port.mk>
