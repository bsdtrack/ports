BROKEN-alpha=	beam/erl_process.c:6692: internal compiler error: in final_scan_insn, at final.c:2449

USE_NOBTCFI=	Yes
USE_WXNEEDED=	Yes

COMMENT-main=	${COMMENT}
COMMENT-wx=	WxWidgets bindings for Erlang

V=		27.3.4.2
DISTNAME=	otp_src_${V}
PORTROACH=	limit:^OTP-27\.
PKGNAME=	erlang-${V}
PKGNAME-main=	erlang-${V}
PKGNAME-wx=	erlang-wx-${V}
EPOCH=		0

VERSION_SPEC=	>=27v0,<28v0
PKGSPEC-main=	erlang-${VERSION_SPEC}
PKGSPEC-wx=	erlang-wx-${VERSION_SPEC}

BUILD_DEPENDS+=	textproc/libxslt

CONFIGURE_STYLE= simple

CONFIGURE_ARGS+=--disable-silent-rules  \
		--without-jinterface	\
		--without-odbc		\
		--enable-threads	\
		--enable-kernel-poll	\
		--disable-hipe

ALL_TARGET=	all
INSTALL_TARGET=	install

MODGNU_CONFIG_GUESS_DIRS =	${WRKSRC}/erts/autoconf

MULTI_PACKAGES = -main -wx

WANTLIB =	m pthread ${COMPILER_LIBCXX}
WANTLIB-main =	${WANTLIB} c crypto kvm curses util z

WANTLIB-wx += ${WANTLIB} GL GLU
WANTLIB-wx += wx_baseu-3.2 wx_baseu_xml-3.2 wx_gtk3u_aui-3.2
WANTLIB-wx += wx_gtk3u_core-3.2 wx_gtk3u_gl-3.2 wx_gtk3u_html-3.2
WANTLIB-wx += wx_gtk3u_stc-3.2 wx_gtk3u_xrc-3.2
WANTLIB-wx += glib-2.0 intl

LIB_DEPENDS-wx +=x11/wxWidgets>=2.8.12p10
LIB_DEPENDS-wx +=devel/glib2

.if ${MACHINE_ARCH} != "alpha" && ${MACHINE_ARCH} != "arm" && \
	${MACHINE_ARCH} != "hppa"
LIB_DEPENDS-wx +=x11/wxWidgets,-webview
WANTLIB-wx += wx_gtk3u_webview-3.2
.endif

RUN_DEPENDS-wx =${BASE_PKGPATH},-main>=${MAJ_V}

DOC_DIR=	${PREFIX}/lib/erlang${MAJ_V}/
FAKE_FLAGS =	libdir_suffix="/erlang${MAJ_V}"

AUTOCONF_VERSION = 2.69

UPDATE_PLIST_ARGS = -i V

# Use the target 'gen-versions' to update this list
ERL_VERSIONS=	\
ASN1_VSN        5.3.4.2 \
COMMON_TEST_VSN 1.27.7 \
COMPILER_VSN    8.6.1.1 \
CRYPTO_VSN      5.5.3 \
DEBUGGER_VSN    5.5 \
DIALYZER_VSN    5.3.1 \
DIAMETER_VSN    2.4.1 \
EDOC_VSN        1.3.2 \
EI_VSN          5.5.2 \
ELDAP_VSN       1.2.14.1 \
EMACS_VSN       2.7.0 \
ERL_DOCGEN_VSN  1.5.2 \
ET_VSN          1.7.1 \
EUNIT_VSN       2.9.1 \
FTP_VSN         1.2.3 \
INETS_VSN       9.3.2 \
JINTERFACE_VSN  1.14 \
KERNEL_VSN      10.2.7.2 \
MEGACO_VSN      4.7.2 \
MNESIA_VSN      4.23.5 \
OBSERVER_VSN    2.17 \
ODBC_VSN        2.15 \
OS_MON_VSN      2.10.1 \
PARSETOOLS_VSN  2.6 \
PUBLIC_KEY_VSN  1.17.1.1 \
RELTOOL_VSN     1.0.1 \
RUNTIME_TOOLS_VSN       2.1.1 \
SASL_VSN        4.2.2 \
SNMP_VSN        5.18.2 \
SSH_VSN         5.2.11.2 \
SSL_VSN         11.2.12.2 \
STDLIB_VSN      6.2.2.2 \
SYNTAX_TOOLS_VSN        3.2.2 \
TFTP_VSN        1.2.2 \
TOOLS_VSN       4.1.1 \
WX_VSN          2.4.3 \
XMERL_VSN       2.1.3.1 \
ERTS_VSN        15.2.7.1

.include <bsd.port.mk>
