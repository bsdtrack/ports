VERSION=	3.10.1

EPOCH=		0

REVISION=	2

PORTROACH=	site:https://ftp.fu-berlin.de/unix/mail/postfix/official/
SITES=		${SITE_POSTFIX:=official/}

NEEDS_OPENSSL=	Yes

# used in PLIST to construct @pkgpath matching the built flavour
FLAVOR_STRING=	${FLAVOR_EXT:S/-/,/g}
SUBST_VARS+=	FLAVOR_STRING

.include <bsd.port.mk>
