COMMENT=	fan-made multiplayer Super Mario Bros

V=		continuous
DATA_V =	2023-11-23

PKGNAME=	supermariowar-2023
DISTNAME=	supermariowar-${V}
REVISION= 	0

CATEGORIES=	games

HOMEPAGE=	https://www.swmstuff.net

MAINTAINER=	Theo Bori <nagi@tilde.team>

SITES = 	https://github.com/mmatyas/supermariowar/

DISTFILES = 	archive/refs/tags/${V}${EXTRACT_SUFX} \
		releases/download/continuous/supermariowar_${DATA_V}_linux.zip

PERMIT_PACKAGE=	Yes

WANTLIB+=	c SDL2 enet yaml-cpp

LIB_DEPENDS=	devel/sdl2 \
		devel/sdl2-image \
		devel/sdl2-mixer \
		net/enet \
		devel/yaml-cpp

MODULES=	devel/cmake

NO_TEST= 	Yes

CONFIGURE_STYLE=	cmake
CONFIGURE_ARGS=		-DBUILD_STATIC_LIBS="OFF"

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/games

.for p in smw smw-leveledit smw-worldedit
	${INSTALL_PROGRAM} ${WRKBUILD}/Binaries/Release/${p} ${PREFIX}/games/${p}
	${SUBST_CMD} -c -m 755 ${FILESDIR}/${p} ${PREFIX}/bin/${p}
.endfor

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/smw
	cp -r ${WRKDIR}/supermariowar/data ${PREFIX}/share/smw/data

.include <bsd.port.mk>
