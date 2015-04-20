# RPM and YUM Cheatshit

[RPM Cheatshit](http://www.tecmint.com/20-practical-examples-of-rpm-commands-in-linux/)

[Red Hat yum cheatshit](https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf)

# Autotools
Autotools = automake + autoconf + libtool

## Primaries for Makefile.am

- **PROGRAMS**
- **LIBRARIES**
- **LISP**
- **PYTHON**
- **JAVA**
- **SCRIPTS**
- **DATA**
- **HEADERS**
- **MANS**
- **TEXINFOS**

## Standard prefixes for Makefile.am and configure.ac
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
- pkgdatadir
- pkgincludedir
- pkglibdir

## Special meaning prefixes
- check - The check prefix indicates products that are built only for testing purposes, and thus will not be installed at all.
- noinst - The noinst prefix indicates that the listed products should be built, but not installed.
- EXTRA - used to list programs that are conditionally built. Usually used to include directory recursivelly

## "Super" prefixes
- dist - indicates a set of files that should be distributed (that is, included in the distribution package when "make dist" is executed).


# RPM
## Build Macros
- %{_sysconfdir}        /etc
- %{_prefix}            /usr
- %{_exec_prefix}       %{_prefix}
- %{_bindir}            %{_exec_prefix}/bin
- %{_libdir}            %{_exec_prefix}/%{_lib}
- %{_libexecdir}        %{_exec_prefix}/libexec
- %{_sbindir}           %{_exec_prefix}/sbin
- %{_sharedstatedir}    /var/lib
- %{_datarootdir}       %{_prefix}/share
- %{_datadir}           %{_datarootdir}
- %{_includedir}        %{_prefix}/include
- %{_infodir}           /usr/share/info
- %{_mandir}            /usr/share/man
- %{_localstatedir}     /var
- %{_initddir}          %{_sysconfdir}/rc.d/init.d
- %{_var}               /var
- %{_tmppath}           %{_var}/tmp
- %{_usr}               /usr
- %{_usrsrc}            %{_usr}/src
- %{_lib}               lib (lib64 on 64bit multilib systems)
- %{_docdir}            %{_datadir}/doc
- %{buildroot}          %{_buildrootdir}/%{name}-%{version}-%{release}.%{_arch}
- $RPM_BUILD_ROOT       %{buildroot}

### Compile a package
```./autogen.sh ; ./configure```

### Create a distribution(tarball)
```./autogen.sh ; ./configure; make dist```

### Check a distribution before release
```./autogen.sh ; ./configure; make distcheck```

### Install a package to a tmp directory for tests
```
DESTDIR=/tmp/test-installation make install
DESTDIR=/tmp/test-installation make install
```

### Build SRPM from tarball
```./autogen.sh ; ./configure; make distcheck; rpmbuild -ts *.tar.gz```

### Build RPM from a SRPM
```./autogen.sh ; ./configure; make distcheck; rpmbuild --rebuild *.src.rpm```

### Build RPM from a tarball
```./autogen.sh ; ./configure; make distcheck; rpmbuild -tb *.tar.gz```

