-include $(top_srcdir)/build/modmake.rulesam
AUTOMAKE_OPTIONS = foreign subdir-objects
MODNAME=mod_abstraction

LIBS := $(if $(switch_builddir),$(switch_builddir)/libfreeswitch.la,)

mod_LTLIBRARIES = mod_abstraction.la
mod_abstraction_la_SOURCES  = mod_abstraction.c
mod_abstraction_la_CFLAGS   = $(AM_CFLAGS) $(FREESWITCH_CFLAGS)
mod_abstraction_la_LIBADD   = $(LIBS)
mod_abstraction_la_LDFLAGS  = -avoid-version -module -no-undefined -shared $(FREESWITCH_LIBS)
