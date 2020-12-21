# $FreeBSD:$

PORTNAME=	k8s-mq-api
PORTVERSION=	0.1
CATEGORIES=	sysutils

MAINTAINER=	olevole@olevole.ru
COMMENT=	Simple demo/sample for CBSD K8S API

LICENSE=	BSD
USES=		go

PLIST_FILES=	bin/k8s-mq-api

USE_GITHUB=	yes
GH_TAGNAME=	c03fce6
GH_ACCOUNT=	k8s-bhyve
GH_PROJECT=	k8s-mq-api
USE_RC_SUBR=	k8s-mq-api

GH_TUPLE=	beanstalkd:go-beanstalk:master:beanstalkd/src/github.com/beanstalkd/go-beanstalk \
		gorilla:mux:v1.8.0:mux/src/github.com/gorilla/mux

post-extract:
	${LN} -sf ${WRKSRC}/src ${WRKDIR}
	${LN} -sf ${WRKSRC} ${WRKDIR}/src/${PORTNAME}

do-install:
	${INSTALL_PROGRAM} ${WRKDIR}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/k8s-mq-api

.include <bsd.port.mk>
