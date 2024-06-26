PORTNAME=	hiptext
PORTVERSION=	0.0.s20160621
PORTREVISION=	16
CATEGORIES=	graphics

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Tool for rendering images and videos inside terminals
WWW=		https://github.com/jart/hiptext

LICENSE=	APACHE20

BUILD_DEPENDS=	ragel:devel/ragel
LIB_DEPENDS=	libgflags.so:devel/gflags \
		libglog.so:devel/glog \
		libpng.so:graphics/png \
		libswscale.so:multimedia/ffmpeg4 \
		libfreetype.so:print/freetype2
TEST_DEPENDS=	googletest>=1.7.0:devel/googletest
RUN_DEPENDS=	${LOCALBASE}/share/fonts/dejavu/DejaVuSans.ttf:x11-fonts/dejavu

USE_GITHUB=	yes
GH_ACCOUNT=	jart
GH_TAGNAME=	f89b44f

USES=		compiler:c++14-lang gmake jpeg localbase
CPPFLAGS+=	-I${LOCALBASE}/include/freetype2
CPPFLAGS+=	-I${LOCALBASE}/ffmpeg4/include
CXXFLAGS+=	-DGLOG_USE_GLOG_EXPORT
LDFLAGS+=	-L${LOCALBASE}/lib -lfreetype
LDFLAGS+=	-L${LOCALBASE}/ffmpeg4/lib
MAKE_ENV=	GTEST_DIR="${LOCALBASE}" \
		TARGET_ARCH=""
TEST_TARGET=	check

PLIST_FILES=	bin/hiptext

post-extract:
	@${RM} -r ${WRKSRC}/gtest

post-patch:
	@${REINPLACE_CMD} -e 's|"DejaVuSansMono.ttf"|"${LOCALBASE}/share/fonts/dejavu/DejaVuSansMono.ttf"|' \
		${WRKSRC}/font.cc

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/hiptext ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
