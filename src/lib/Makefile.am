if PLATFORM_WIN32
version_info = -version-info $(LT_CURRENT):$(LT_REVISION):$(LT_AGE) -avoid-version
else
version_info = -version-info $(LT_CURRENT):$(LT_REVISION):$(LT_AGE)
endif

lib_LTLIBRARIES = libwpg-@WPG_MAJOR_VERSION@.@WPG_MINOR_VERSION@.la

AM_CXXFLAGS = -I$(top_srcdir)/inc $(REVENGE_CFLAGS) $(WPD_CFLAGS) $(DEBUG_CXXFLAGS) -DLIBWPG_BUILD=1

if HAVE_VISIBILITY
AM_CXXFLAGS += -fvisibility=hidden -DLIBWPG_VISIBILITY
endif

libwpg_@WPG_MAJOR_VERSION@_@WPG_MINOR_VERSION@_la_LIBADD  = $(WPD_LIBS) $(REVENGE_LIBS) @LIBWPG_WIN32_RESOURCE@
libwpg_@WPG_MAJOR_VERSION@_@WPG_MINOR_VERSION@_la_DEPENDENCIES = @LIBWPG_WIN32_RESOURCE@
libwpg_@WPG_MAJOR_VERSION@_@WPG_MINOR_VERSION@_la_LDFLAGS = $(version_info) -export-dynamic -no-undefined
libwpg_@WPG_MAJOR_VERSION@_@WPG_MINOR_VERSION@_la_SOURCES = \
	WPG1Parser.cpp \
	WPG1Parser.h \
	WPG2Parser.cpp \
	WPG2Parser.h \
	WPGBitmap.cpp \
	WPGBitmap.h \
	WPGColor.cpp \
	WPGColor.h \
	WPGDashArray.cpp \
	WPGDashArray.h \
	WPGHeader.cpp \
	WPGHeader.h \
	WPGTextDataHandler.cpp \
	WPGTextDataHandler.h \
	WPGXParser.cpp \
	WPGXParser.h \
	WPGraphics.cpp \
	libwpg_utils.cpp \
	libwpg_utils.h

if OS_WIN32

@LIBWPG_WIN32_RESOURCE@ : libwpg.rc $(libwpg_@WPG_MAJOR_VERSION@_@WPG_MINOR_VERSION@_la_OBJECTS)
	chmod +x $(top_srcdir)/build/win32/*compile-resource
	WINDRES=@WINDRES@ $(top_srcdir)/build/win32/lt-compile-resource libwpg.rc @LIBWPG_WIN32_RESOURCE@

endif

EXTRA_DIST = \
	libwpg.rc.in \
	libwpg.rc
