COMMENT=	Classic WW1 biplane game

V=		2.4.0
DISTNAME=	sdl-sopwith-${V}
#DISTNAME=	${PKGNAME}
REVISION= 	0

CATEGORIES=	games

HOMEPAGE=	https://fragglet.github.io/sdl-sopwith/

MAINTAINER=	Theo Bori <nagi@tilde.team>

SITES=		https://github.com/fragglet/sdl-sopwith/releases/download/sdl-sopwith-2.4.0/

# GPL-2.0
PERMIT_PACKAGE=	Yes

CONFIGURE_STYLE=	autoreconf
AUTOCONF_VERSION=	2.71
AUTOMAKE_VERSION=	1.16

WANTLIB+=	c X11 SDL2

LIB_DEPENDS=	devel/sdl2

USE_GMAKE=	Yes

NO_TEST= 	Yes

.include <bsd.port.mk>
