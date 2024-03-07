COMMENT=	fan-made multiplayer Super Mario Bros

V=		continuous
DATA_V =	2023-11-23

PKGNAME=	supermariowar-2023
DISTNAME=	supermariowar-${V}
#WRKDIST=	${WRKDIR}/supermariowar-${V}
REVISION= 	0

CATEGORIES=	games

HOMEPAGE=	https://www.swmstuff.net

MAINTAINER=	Theo Bori <nagi@tilde.team>

SITES = 	https://github.com/mmatyas/supermariowar/

DISTFILES = 	archive/refs/tags/${V}${EXTRACT_SUFX} \
		releases/download/continuous/supermariowar_${DATA_V}_linux.zip

# Bsd-like
PERMIT_PACKAGE=	Yes

WANTLIB+=	c SDL2

LIB_DEPENDS=	devel/sdl2 \
		devel/sdl2-image \
		devel/sdl2-mixer \
		net/enet \
		devel/yaml-cpp

MODULES=	devel/cmake

NO_TEST= 	Yes

CONFIGURE_STYLE=	cmake
CONFIGURE_ARGS=		-DBUILD_STATIC_LIBS="OFF"

post-install:
	mv ${WRKDIR}/supermariowar/data ${PREFIX}/games/smw_data

.include <bsd.port.mk>
