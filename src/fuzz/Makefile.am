noinst_PROGRAMS = wpgfuzzer

AM_CXXFLAGS = -I$(top_srcdir)/inc \
	$(REVENGE_GENERATORS_CFLAGS) \
	$(REVENGE_CFLAGS) \
	$(REVENGE_STREAM_CFLAGS) \
	$(DEBUG_CXXFLAGS)

wpgfuzzer_LDADD = \
	$(top_builddir)/src/lib/libwpg-@WPG_MAJOR_VERSION@.@WPG_MINOR_VERSION@.la \
	$(REVENGE_GENERATORS_LIBS) \
	$(REVENGE_LIBS) \
	$(REVENGE_STREAM_LIBS) \
	-lFuzzingEngine

wpgfuzzer_SOURCES = \
	wpgfuzzer.cpp
