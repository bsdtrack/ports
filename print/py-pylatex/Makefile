COMMENT=		Python interface for LaTeX

MODPY_EGG_VERSION=	1.4.1
DISTNAME=		PyLaTeX-${MODPY_EGG_VERSION}
PKGNAME=		py-pylatex-${MODPY_EGG_VERSION}
REVISION=		1

CATEGORIES=		print

MAINTAINER=		Clemens Goessnitzer <clemens@goessnitzer.info>

HOMEPAGE=		https://github.com/JelteF/PyLaTeX

# MIT
PERMIT_PACKAGE=		Yes

MODULES=		lang/python

FLAVORS=		python3
FLAVOR=			python3

MODPY_PYBUILD=		setuptools
MODPY_PI=		Yes

RUN_DEPENDS=		devel/py-ordered-set${MODPY_FLAVOR} \
			print/texlive/texmf,-full

.include <bsd.port.mk>
