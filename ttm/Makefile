# $FreeBSD$

.PATH:	${.CURDIR}

KMOD=	ttm
SRCS=	ttm_agp_backend.c \
	ttm_lock.c \
	ttm_object.c \
	ttm_tt.c \
	ttm_bo_util.c \
	ttm_bo.c \
	ttm_bo_manager.c \
	ttm_execbuf_util.c \
	ttm_memory.c \
	ttm_module.c \
	ttm_page_alloc.c \
	ttm_page_alloc_dma.c \
	ttm_bo_vm.c

CFLAGS+= -I${.CURDIR:H}/linuxkpi/dummy/include
CFLAGS+= -I${.CURDIR:H}/linuxkpi/gplv2/include
CFLAGS+= -I${SYSDIR}/compat/linuxkpi/common/include
CFLAGS+= -I${.CURDIR}
CFLAGS+= -I${.CURDIR}/ttm
CFLAGS+= -I${.CURDIR:H}/include
CFLAGS+= -I${.CURDIR:H}/include/drm
CFLAGS+= -I${.CURDIR:H}/include/uapi
CFLAGS+= -I${.CURDIR:H}
CFLAGS+= '-DKBUILD_MODNAME="${KMOD}"'

CFLAGS+= -include ${.CURDIR:H}/drm/drm_os_config.h

SRCS+=	device_if.h \
	vnode_if.h \
	bus_if.h \
	pci_if.h \
	device_if.h \
	iicbus_if.h \
	opt_drm.h \
	opt_vm.h \
	opt_compat.h \
	opt_syscons.h

.if ${MACHINE_CPUARCH} == "powerpc"
CWARNFLAGS+=-Wno-cast-qual
.endif
CWARNFLAGS+= -Wno-pointer-arith -Wno-pointer-sign -Wno-format
CWARNFLAGS+= -Wno-expansion-to-defined

.include <bsd.kmod.mk>
