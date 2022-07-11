
# Copyright (C) 2006-2008 Junjiro Okajima
# Copyright (C) 2006-2008 Tomas Matejicek, slax.org
#
# LICENSE follows the described ones in lzma and squashfs.

# $Id: Makefile,v 1.30 2008-03-12 16:24:54 jro Exp $

# paths
Sqlzma = ${CURDIR}

LzmaVer = lzma457
Lzma = ${Sqlzma}/${LzmaVer}
SqVer = squashfs3.4
Squashfs = ..
KVer = linux-2.6.26
SqFs = ${Squashfs}/kernel-patches/${KVer}/fs/squashfs
#KDir = /lib/modules/$(shell uname -r)/build
#KDir = ${SqFs}/../..

ifeq (${LzmaVer}, lzma443)
LzmaC = ${Lzma}/C/7zip/Compress/LZMA_C
LzmaAlone = ${Lzma}/C/7zip/Compress/LZMA_Alone
else
LzmaC = ${Lzma}/C/Compress/Lzma
LzmaAlone = ${Lzma}/CPP/7zip/Compress/LZMA_Alone
endif
SqTools = ${Squashfs}/squashfs-tools

# enable it if you want to add -g option when compiling
#UseDebugFlags = 1
#MyDebugFlags = -DSQUASHFS_TRACE
# disable it if you don't want to compile squashfs kernel module here
# BuildSquashfs = 1

export

all:
	${MAKE} -C ${LzmaC} -f sqlzma.mk $@
	${MAKE} -C ${LzmaAlone} -f sqlzma.mk $@
	${MAKE} -C ${SqTools} -f Makefile.squash $@

clean:
	${MAKE} -C ${LzmaC} -f sqlzma.mk $@
	${MAKE} -C ${LzmaAlone} -f sqlzma.mk $@
	${MAKE} -C ${SqTools} -f Makefile.squash $@
	${RM} *~

########################################

-include priv.mk

