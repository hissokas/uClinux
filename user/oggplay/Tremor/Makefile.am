AUTOMAKE_OPTIONS = foreign

INCLUDES = -I./

lib_LTLIBRARIES = libvorbisidec.la

libvorbisidec_la_SOURCES = mdct.c block.c window.c \
                        synthesis.c info.c \
                        floor1.c floor0.c vorbisfile.c \
                        res012.c mapping0.c registry.c codebook.c \
			sharedbook.c framing.c bitwise.c \
                        codebook.h misc.h mdct_lookup.h\
                        os.h mdct.h ivorbisfile.h lsp_lookup.h\
                        registry.h window.h lookup_data.h\
                        codec_internal.h backends.h ogg.h \
			asm_arm.h ivorbiscodec.h
libvorbisidec_la_LDFLAGS = -version-info @V_LIB_CURRENT@:@V_LIB_REVISION@:@V_LIB_AGE@

EXTRA_PROGRAMS = ivorbisfile_example
CLEANFILES = $(EXTRA_PROGRAMS) $(lib_LTLIBRARIES)

ivorbisfile_example_SOURCES = ivorbisfile_example.c
ivorbisfile_example_LDFLAGS = -static 
ivorbisfile_example_LDADD = libvorbisidec.la

debug:
	$(MAKE) all CFLAGS="@DEBUG@" LDFLAGS="-lefence"	

profile:
	$(MAKE) all CFLAGS="@PROFILE@"
