PORTNAME=	sassc-rails
PORTVERSION=	2.1.2
PORTREVISION=	3
CATEGORIES=	textproc rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	-rails60

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Integrate SassC-Ruby into Rails
WWW=		https://github.com/sass/sassc-rails

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	rubygem-railties60>=4.0.0:www/rubygem-railties60 \
		rubygem-sassc>=2.0:textproc/rubygem-sassc \
		rubygem-sprockets-rails-rails60>=0:devel/rubygem-sprockets-rails-rails60 \
		rubygem-sprockets3>=3.0:devel/rubygem-sprockets3 \
		rubygem-tilt>=0:devel/rubygem-tilt

USES=		gem

NO_ARCH=	yes

.include <bsd.port.mk>
