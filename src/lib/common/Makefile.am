MAINTAINERCLEANFILES = 		$(srcdir)/Makefile.in

AM_CPPFLAGS =                   -I$(srcdir)/../cryptoki_compat \
				-I$(srcdir)/../crypto \
				-I$(srcdir)/../data_mgr \
				-I$(srcdir)/..

noinst_LTLIBRARIES =		libsofthsm_common.la
libsofthsm_common_la_SOURCES =	Configuration.cpp \
				fatal.cpp \
				log.cpp \
				osmutex.cpp \
				SimpleConfigLoader.cpp \
				MutexFactory.cpp

man_MANS =			softhsm2.conf.5

EXTRA_DIST =			$(srcdir)/*.h \
				$(srcdir)/softhsm2.conf.5.in

install-data-hook:
	test -d ${DESTDIR}${sysconfdir} || \
		${INSTALL} -d ${DESTDIR}${sysconfdir}
	test -f ${DESTDIR}${sysconfdir}/softhsm2.conf || \
		${INSTALL_DATA} ${top_builddir}/src/lib/common/softhsm2.conf ${DESTDIR}${sysconfdir}
	${INSTALL_DATA} ${top_builddir}/src/lib/common/softhsm2.conf ${DESTDIR}${sysconfdir}/softhsm2.conf.sample
	test -d ${DESTDIR}${softhsmtokendir} || \
		${INSTALL} -d -m 700 ${DESTDIR}${softhsmtokendir}
