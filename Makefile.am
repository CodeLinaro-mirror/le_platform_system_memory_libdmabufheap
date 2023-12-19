AM_CPPFLAGS := \
    -W \
    -Wall \
    -Wextra \
    -Wunused \
    -Wno-missing-field-initializers

ACLOCAL_AMFLAGS = -I m4

libdmabuf_sources = BufferAllocator.cpp BufferAllocatorWrapper.cpp

# Build libdmabufheap.so
lib_LTLIBRARIES = libdmabufheap.la

libdmabufheap_la_SOURCES := $(libdmabuf_sources)
libdmabufheap_la_CPPFLAGS := -I$(top_srcdir)/include
libdmabufheap_la_CPPFLAGS += $(AM_CPPFLAGS) -Wno-error=pointer-to-int-cast
libdmabufheap_la_CPPFLAGS += -std=c++17

libdmabufheap_la_CPPFLAGS +=  @LIBION_CFLAGS@
libdmabufheap_la_LDFLAGS :=  @LIBION_LIBS@

# Export headers
dmabufheap_includedir=$(includedir)/BufferAllocator
dmabufheap_include_HEADERS := include/BufferAllocator/BufferAllocator.h
dmabufheap_include_HEADERS += include/BufferAllocator/BufferAllocatorWrapper.h
dmabufheap_include_HEADERS += include/BufferAllocator/dmabufheap-defs.h

pkgconfigdir := $(libdir)/pkgconfig
pkgconfig_DATA := libdmabufheap.pc
EXTRA_DIST := $(pkgconfig_DATA)
