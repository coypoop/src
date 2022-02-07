#	$NetBSD: Makefile,v 1.7 2017/06/05 18:54:30 christos Exp $

NOMAN=	# defined
.include "bsd.own.mk"

IDIST=	${NETBSDSRCDIR}/external/bsd/bsdec2-image-upload/dist
.PATH:	${IDIST}/bsdec2-image-upload \
	${IDIST}/libcperciva/aws \
	${IDIST}/libcperciva/alg \
	${IDIST}/libcperciva/datastruct \
	${IDIST}/libcperciva/util \
	${IDIST}/lib/util

BINDIR?= /usr/bin

PROG=	bsdec2-image-upload
SRCS=	main.c sha256.c elasticarray.c entropy.c \
	hexify.c insecure_memzero.c warnp.c \
	aws_readkeys.c aws_sign.c \
	rfc3986.c sslreq.c \
	getopt.c asprintf.c

CPPFLAGS+=	-I${IDIST}/libcperciva/util \
		-I${IDIST}/libcperciva/aws \
		-I${IDIST}/libcperciva/alg \
		-I${IDIST}/libcperciva/datastruct \
		-I${IDIST}/lib/util

DPADD+=	${LIBSSL} ${LIBCRYPTO}
LDADD+=	-lssl -lcrypto

.include <bsd.prog.mk>
