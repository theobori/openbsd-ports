COMMENT=	fast gui x11 autoclicker

V=		1.5.0

PKGNAME=	xclicker-${V}
REVISION= 	0

CATEGORIES=	x11

HOMEPAGE=	https://xclicker.xyz

MAINTAINER=	Theo Bori <nagi@tilde.team>

SITES= 		https://github.com/robiot/xclicker/archive/refs/tags/

DISTFILES= 	v${V}${EXTRACT_SUFX}

WRKSRC= 	${WRKDIST}/${PKGNAME}

# GPL-3.0
PERMIT_PACKAGE=	Yes

MODULES= 	devel/meson

WANTLIB=	X11 c

NO_TEST= 	Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/src/xclicker ${PREFIX}/bin/xclicker

.include <bsd.port.mk>
