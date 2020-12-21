# $FreeBSD:$

PORTNAME=	cbsd-mq-router
PORTVERSION=	0.1
CATEGORIES=	sysutils

MAINTAINER=	olevole@olevole.ru
COMMENT=	CBSD message queue router

LICENSE=	BSD

RUN_DEPENDS=	beanstalkd:net/beanstalkd

USES=		go

PLIST_FILES=	bin/cbsd-mq-router

USE_GITHUB=	yes
GH_TAGNAME=	1605df2
GH_ACCOUNT=	cbsd
GH_PROJECT=	cbsd-mq-router
USE_RC_SUBR=	cbsd-mq-router

GH_TUPLE=	beanstalkd:go-beanstalk:master:beanstalkd/src/github.com/beanstalkd/go-beanstalk \
		golang:crypto:8b5274cf687f:golang_crypto/vendor/golang.org/x/crypto \
		golang:term:2321bbc49cbf:golang_term/vendor/golang.org/x/term \
		golang:sys:7d0127a74742:golang_sys/vendor/golang.org/x/sys

post-extract:
	${LN} -sf ${WRKSRC}/src ${WRKDIR}
	${LN} -sf ${WRKSRC} ${WRKDIR}/src/${PORTNAME}

do-install:
	${INSTALL_PROGRAM} ${WRKDIR}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/cbsd-mq-router

.include <bsd.port.mk>
