COMMENT=	pytest plugin to create CodSpeed benchmarks

MODPY_DISTV=	4.0.0
DISTNAME=	pytest_codspeed-${MODPY_DISTV}
PKGNAME=	py-test-codspeed-${MODPY_DISTV}
CATEGORIES=	devel

HOMEPAGE=	https://github.com/CodSpeedHQ/pytest-codspeed

# MIT
PERMIT_PACKAGE=	Yes

MODULES=	lang/python
MODPY_PI=	Yes
MODPY_PYBUILD=	setuptools

BUILD_DEPENDS=	devel/py-cffi
RUN_DEPENDS=	devel/py-cffi \
		devel/py-rich \
		devel/py-setuptools \
		devel/py-test
# conftest.py missing in sdist
NO_TEST=	Yes

MAKE_ENV=	PYTEST_CODSPEED_SKIP_EXTENSION_BUILD=1

.include <bsd.port.mk>
