PORTNAME=	pass-otp
DISTVERSIONPREFIX=	v
DISTVERSION=	1.2.0
PORTREVISION=	1
CATEGORIES=	sysutils

MAINTAINER=	alex@xanderio.de
COMMENT=	Pass extension for managing one-time-password (OTP) tokens
WWW=		https://github.com/tadfisher/pass-otp

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	bash:shells/bash \
		pass:sysutils/password-store \
		qrencode:graphics/libqrencode \
		oathtool:security/oath-toolkit
TEST_DEPENDS=	expect:lang/expect \
		git:devel/git

USES=		gmake shebangfix
USE_GITHUB=	yes
GH_ACCOUNT=	tadfisher
SHEBANG_FILES=	otp.bash test/*.sh test/*t

NO_ARCH=	yes
NO_BUILD=	yes
MAKE_ENV=	LIBDIR=${PREFIX}/libexec \
		MANDIR=${PREFIX}/share/man \
		BASHCOMPDIR=${PREFIX}/share/bash-completion/completions

TEST_TARGET=	test
TEST_ARGS=	SHELL=${LOCALBASE}/bin/bash

PLIST_FILES=	share/man/man1/pass-otp.1.gz\
		libexec/password-store/extensions/otp.bash \
		share/bash-completion/completions/pass-otp

.include <bsd.port.mk>
