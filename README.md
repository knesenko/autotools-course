# Primaries for **Makefile.am**

- PROGRAMS
- LIBRARIES
- LISP
- PYTHON
- JAVA
- SCRIPTS
- DATA
- HEADERS
- MANS
- TEXINFOS

# Standard targets for Makefile.am and configure.ac
- prefix          = /usr/local
- exec-prefix     = $(prefix)
- bindir          = $(exec_prefix)/bin
- sbindir         = $(exec_prefix)/sbin
- libexecdir      = $(exec_prefix)/libexec
- datarootdir     = $(prefix)/share
- datadir         = $(datarootdir)
- sysconfdir      = $(prefix)/etc
- sharedstatedir  = $(prefix)/com
- localstatedir   = $(prefix)/var
- includedir      = $(prefix)/include
- oldincludedir   = /usr/include
- docdir          = $(datarootdir)/doc/$(package)
- infodir         = $(datarootdir)/info
- htmldir         = $(docdir)
- dvidir          = $(docdir)
- pdfdir          = $(docdir)
- psdir           = $(docdir)
- libdir          = $(exec_prefix)/lib
- lispdir         = $(datarootdir)/emacs/site-lisp
- localedir       = $(datarootdir)/locale
- mandir          = $(datarootdir)/man
- manNdir         = $(mandir)/manN  (N = 1..9)
- manext          = .1
- manNext         = .N              (N = 1..9)
- srcdir          = (compiled project root)
