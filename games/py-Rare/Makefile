PORTNAME=	Rare
PORTVERSION=	1.10.3
CATEGORIES=	games
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ffqq@danwin1210.de
COMMENT=	GUI for legendary. An Epic Games Launcher open source alternative
WWW=		https://github.com/Dummerle/Rare

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}wheel>=0:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools>0:devel/py-setuptools@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}psutil>0:sysutils/py-psutil@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>0:www/py-requests@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}legendary-gl>0:games/py-legendary-gl@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}QtAwesome>0:x11-fonts/py-QtAwesome@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}typing-extensions>0:devel/py-typing-extensions@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}qt5>=0:devel/py-qt5@${PY_FLAVOR}

ONLY_FOR_ARCHS=	amd64
USES=		python desktop-file-utils
USE_GITHUB=	yes
GH_ACCOUNT=	Dummerle
GH_PROJECT=	${PORTNAME}
GH_TAGNAME=	${PORTVERSION}
USE_PYTHON=	distutils autoplist
PLIST_FILES+=	share/applications/rare.desktop

post-build:
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/applications
	(cd ${WRKDIR} && ${INSTALL_DATA} ${FILESDIR}/rare.desktop \
		${STAGEDIR}${PREFIX}/share/applications)

.include <bsd.port.mk>
