COMMENT =	Symas Lightning Memory-Mapped Database

VERSION =	0.9.32
REVISION =	0

DISTNAME =	openldap-LMDB_${VERSION}
PKGNAME =	lmdb-${VERSION}

SHARED_LIBS +=  lmdb                      0.0 # 0.0

CATEGORIES =	databases

HOMEPAGE =	https://symas.com/lmdb/

MAINTAINER =	Jeremie Courreges-Anglas <jca@wxcvbn.org>

# OpenLDAP Public License
PERMIT_PACKAGE =	Yes

WANTLIB += c pthread

SITES =	https://git.openldap.org/openldap/openldap/-/archive/LMDB_${VERSION}/

DEBUG_PACKAGES =	${BUILD_PACKAGES}

USE_GMAKE =		Yes

MAKE_FLAGS =		CC="${CC}" XCFLAGS="${CFLAGS}" \
			SHARED_VERSION_MAJOR=${LIBlmdb_VERSION:R} \
			SHARED_VERSION_MINOR=${LIBlmdb_VERSION:E}

WRKDIST =		${WRKDIR}/openldap-LMDB_${VERSION}/libraries/liblmdb

SUBST_VARS +=	VERSION

# lmdb.pc: https://bugs.openldap.org/show_bug.cgi?id=10203
post-install:
	! test -e ${PREFIX}/lib/pkgconfig/lmdb.pc # fail if shipped upstream
	${SUBST_CMD} -c -o ${SHAREOWN} -g ${SHAREGRP} -m ${SHAREMODE} \
	    ${FILESDIR}/lmdb.pc.in ${PREFIX}/lib/pkgconfig/lmdb.pc

.include <bsd.port.mk>
