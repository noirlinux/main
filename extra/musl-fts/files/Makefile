PREFIX = /usr/local
LIBDIR = ${PREFIX}/lib
INCDIR = ${PREFIX}/include
PKGCONFDIR = ${LIBDIR}/pkgconfig
CC      ?= cc
AR      ?= ar
RANLIB  ?= ranlib

CPPFLAGS = -DHAVE_CONFIG_H -I.

all: libfts.a libfts.so.0.0.0

fts.o: fts.c
	${CC} ${CFLAGS} ${CPPFLAGS} -c -o fts.o fts.c

libfts.a: fts.o
	${AR} cru libfts.a fts.o
	${RANLIB} libfts.a

libfts.so.0.0.0: fts.o
	${CC} -shared -fPIC -DPIC fts.o ${CFLAGS} -Wl,-soname -Wl,libfts.so.0 -o libfts.so.0.0.0

install: all
	mkdir -p ${DESTDIR}${INCDIR} ${DESTDIR}${PKGCONFDIR}
	cp libfts.a libfts.so.0.0.0 ${DESTDIR}${LIBDIR}
	cp musl-fts.pc ${DESTDIR}${PKGCONFDIR}
	cp fts.h ${DESTDIR}${INCDIR}
	chmod 644 ${DESTDIR}${INCDIR}/fts.h ${DESTDIR}${LIBDIR}/libfts.a ${DESTDIR}${PKGCONFDIR}/musl-fts.pc
	chmod 755 ${DESTDIR}${LIBDIR}/libfts.so.0.0.0
	ln -sf libfts.so.0.0.0 ${DESTDIR}${LIBDIR}/libfts.so.0
	ln -sf libfts.so.0     ${DESTDIR}${LIBDIR}/libfs.so

.PHONY: all
