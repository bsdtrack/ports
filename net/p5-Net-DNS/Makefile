COMMENT =	perl interface to the domain name system

DISTNAME =	Net-DNS-1.51
SUPDISTFILES =	${DISTFILES}.asc

CATEGORIES =	net

HOMEPAGE =	https://www.net-dns.org/

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# MIT
PERMIT_PACKAGE =	Yes

SITES =			https://www.net-dns.org/download/

MODULES =		cpan

RUN_DEPENDS =		security/p5-Digest-HMAC>=1.03
TEST_DEPENDS =		devel/p5-Test-Pod>=1.45 \
			net/p5-Net-DNS-SEC>=1.01 \
			net/p5-Net-LibIDN>=0.12 \
			security/p5-Digest-BubbleBabble>=0.02

CONFIGURE_ARGS =	--noonline-tests

PKG_ARCH =		*

MODCPAN_EXAMPLES =	Yes
MODCPAN_EXAMPLES_DIST =	demo

.include <bsd.port.mk>
