DISTNAME =	harec-${V}
DISTFILES =	harec-{harec/archive/}${V}${EXTRACT_SUFX}

WANTLIB += c m

# C11
COMPILER =	base-clang ports-gcc
COMPILER_LANGS =	c

BUILD_DEPENDS =	${RUN_DEPENDS}

RUN_DEPENDS =	lang/qbe

# All archs need a newer GNU as
# gas-2.31.1 is not new enough for riscv64
.if ${MACHINE_ARCH:Mriscv64}
RUN_DEPENDS +=	devel/binutils
.else
RUN_DEPENDS +=	devel/gas
.endif

CONFIGURE_ENV =		AS="gas"

do-gen:
	cp ${WRKSRC}/configs/openbsd.mk ${WRKSRC}/config.mk
.if ${MACHINE_ARCH:Maarch64} || ${MACHINE_ARCH:Mriscv64}
	sed -i "s/x86_64/$$(arch -s)/g" ${WRKSRC}/config.mk
.endif

TEST_TARGET =	check

.include <bsd.port.mk>
