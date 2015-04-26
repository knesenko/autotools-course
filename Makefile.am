AUTOMAKE_OPTIONS = foreign 1.9
ACLOCAL_AMFLAGS = -I m4

MAINTAINERCLEANFILES = \
	config.log config.status \
	$(srcdir)/Makefile.in \
	$(srcdir)/configure \
	$(srcdir)/install-sh $(srcdir)/missing \
	$(srcdir)/depcomp $(srcdir)/py-compile \
	$(srcdir)/config.guess $(srcdir)/config.sub \
	$(srcdir)/config.rpath \
	$(srcdir)/ABOUT-NLS \
	$(srcdir)/aclocal.m4 \
	$(NULL)

SUBDIRS = \
	src \
	$(NULL)

dist_doc_DATA = \
	AUTHORS \
	README.md \
	$(NULL)

dist_noinst_DATA = \
	knesenko.spec \
	$(NULL)

dist_noinst_SCRIPTS = \
	autogen.sh \
	$(NULL)
