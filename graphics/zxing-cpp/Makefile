COMMENT=	C++ barcode image processing library

GH_ACCOUNT=	zxing-cpp
GH_PROJECT=	zxing-cpp
# 2.3.0 depends on a newer libcxx
GH_TAGNAME=	v2.2.1
REVISION=	0

SHARED_LIBS +=  ZXing                     2.0 # 0.0

MAINTAINER =	Rafael Sadowski <rsadowski@openbsd.org>

CATEGORIES=	graphics

# Apache 2.0
PERMIT_PACKAGE=	Yes

# C++17
COMPILER=	base-clang ports-gcc

WANTLIB += ${COMPILER_LIBCXX} m

MODULES=	devel/cmake

DEBUG_PACKAGES=	${BUILD_PACKAGES}

BUILD_DEPENDS=	devel/gtest

CONFIGURE_ARGS=		-DCMAKE_LIBRARY_PATH=${LOCALBASE}/lib \
			-DBUILD_UNIT_TESTS=yes

CONFIGURE_ARGS +=	-DCMAKE_DISABLE_FIND_PACKAGE_Git=ON \
			-DBUILD_DEPENDENCIES=LOCAL

# Depends on stb
CONFIGURE_ARGS +=	-DBUILD_EXAMPLES=OFF

.include <bsd.port.mk>
