include $(top_srcdir)/build/python.inc

MAINTAINERCLEANFILES = \
	$(srcdir)/Makefile.in \
	$(NULL)

dist_pkgdata_SCRIPTS = \
	test.sh \
	$(NULL)

dist_autotoolslib_PYTHON = \
	test.py \
	$(NULL)

clean-local: \
	python-clean \
	$(NULL)

all-local: \
	$(DISTFILES) \
	python-syntax-check \
	$(NULL)
