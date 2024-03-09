COMMENT=	puzzle-platform game

V=		2.4.1
NAME=		VVVVVV
PKGNAME= 	${NAME}-${V}

CATEGORIES=	games

HOMEPAGE=	http://thelettervsixtim.es

MAINTAINER=	Theo Bori <nagi@tilde.team>

EXTRACT_SUFX=	.zip

WRKSRC=		${WRKDIST}/${NAME}/desktop_version

SITES= 		https://github.com/terrycavanagh/${NAME}/releases/download/${V}/
SITES.a=	${HOMEPAGE}/makeandplay/

DISTFILES=	${PKGNAME}${EXTRACT_SUFX}
DISTFILES.a=	vvvvvv-mp-linux-02132024${EXTRACT_SUFX}

# Bsd-like
PERMIT_PACKAGE=	Yes

WANTLIB+=	c SDL2 physfs tinyxml2 FAudio

LIB_DEPENDS=	devel/sdl2 \
		devel/physfs \
		audio/faudio \
		textproc/tinyxml2

CXXFLAGS+= 	-I${PREFIX}/include

MODULES=	devel/cmake

CONFIGURE_ARGS=		-DBUNDLE_DEPENDENCIES="OFF"

do-extract:
	unzip ${FULLDISTDIR}/${PKGNAME}${EXTRACT_SUFX} -d ${WRKDIR}/
	unzip ${FULLDISTDIR}/vvvvvv-mp-linux-02132024${EXTRACT_SUFX} -d ${WRKDIR}/${PKGNAME}-data

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/games/${NAME}
	${INSTALL_PROGRAM} ${WRKBUILD}/${NAME} ${PREFIX}/games/${NAME}/${NAME}

	${SUBST_CMD} -c -m 755 ${FILESDIR}/${NAME} ${PREFIX}/bin/${NAME}

post-install:
	${INSTALL_DATA} ${WRKDIR}/${PKGNAME}-data/data.zip ${PREFIX}/games/${NAME}

	${INSTALL_DATA_DIR} ${PREFIX}/share/${NAME}

.for d in lang licenses fonts
	cp -r ${WRKDIR}/${PKGNAME}-data/${d} ${PREFIX}/share/${NAME}
.endfor

.include <bsd.port.mk>

