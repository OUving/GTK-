## Process this file with automake to produce Makefile.in
include $(top_srcdir)/Makefile.decl

libgdkincludedir = $(includedir)/gtk-3.0/gdk
libgdkx11includedir = $(includedir)/gtk-3.0/gdk/x11

INCLUDES = 			\
	-DG_LOG_DOMAIN=\"Gdk\"	\
	-DGDK_COMPILATION	\
	-I$(top_srcdir)		\
	-I$(top_srcdir)/gdk	\
	-I$(top_builddir)/gdk	\
	$(GTK_DEBUG_FLAGS) 	\
	$(GDK_DEP_CFLAGS)

LDADDS = $(GDK_DEP_LIBS)

noinst_LTLIBRARIES = libgdk-x11.la

libgdk_x11_la_SOURCES = 	\
	MwmUtil.h		\
	gdkapplaunchcontext-x11.c \
	gdkasync.c		\
	gdkasync.h		\
	gdkcursor-x11.c		\
	gdkdevice-core-x11.c	\
	gdkdeviceprivate-xi.h	\
	gdkdevicemanager-core-x11.c \
	gdkdevicemanager-x11.c	\
	gdkdevicemanagerprivate-core.h \
	gdkdisplaymanager-x11.c	\
	gdkdisplay-x11.c	\
	gdkdisplay-x11.h	\
	gdkdnd-x11.c		\
	gdkeventsource.c	\
	gdkeventsource.h	\
	gdkeventtranslator.c	\
	gdkeventtranslator.h	\
	gdkgeometry-x11.c  	\
	gdkkeys-x11.c		\
	gdkmain-x11.c		\
	gdkproperty-x11.c	\
	gdkscreen-x11.c		\
	gdkscreen-x11.h		\
	gdkselection-x11.c	\
	gdktestutils-x11.c	\
	gdkvisual-x11.c		\
	gdkwindow-x11.c		\
	gdkwindow-x11.h		\
	gdkxftdefaults.c	\
	gdkxid.c		\
	gdkx.h			\
	gdkprivate-x11.h	\
	xsettings-client.h	\
	xsettings-client.c	\
	xsettings-common.h	\
	xsettings-common.c

libgdkx11include_HEADERS =

if XINPUT_XFREE
libgdk_x11_la_SOURCES += 	\
	gdkdevicemanager-xi.c	\
	gdkdevice-xi.c
libgdkx11include_HEADERS +=	\
	gdkx11devicemanager-xi.h \
	gdkx11device-xi.h
if XINPUT_2
libgdk_x11_la_SOURCES += 	\
	gdkdevicemanager-xi2.c	\
	gdkdevice-xi2.c
libgdkx11include_HEADERS +=	\
	gdkx11devicemanager-xi2.h \
	gdkx11device-xi2.h
endif
endif


libgdkinclude_HEADERS = 	\
	gdkx.h

libgdkx11include_HEADERS += 	\
	gdkx11applaunchcontext.h \
	gdkx11cursor.h		\
	gdkx11device-core.h	\
	gdkx11devicemanager-core.h \
	gdkx11display.h		\
	gdkx11displaymanager.h	\
	gdkx11dnd.h		\
	gdkx11keys.h		\
	gdkx11property.h	\
	gdkx11screen.h		\
	gdkx11selection.h	\
	gdkx11utils.h		\
	gdkx11visual.h		\
	gdkx11window.h

noinst_PROGRAMS = checksettings
checksettings_LDADD = libgdk-x11.la $(GLIB_LIBS)

TESTS = checksettings

# We need to include all these C files here since the conditionals
# don't seem to be correctly expanded for the dist files.
EXTRA_DIST += 			\
	gdksettings.c

-include $(top_srcdir)/git.mk
