AC_PREREQ([2.71])
AC_INIT([psec], [0.4], [bugs@kara-online.net])

#host switch
AC_CANONICAL_HOST
AS_CASE(["$host_os"],
  [*linux*], [
    OS_VERSION=linux
    AC_DEFINE([OS_LINUX], [],
      [Defined if the target OS is Linux])
  ],
  [*mingw*|*cygwin*], [
    OS_VERSION=windows
    AC_DEFINE([OS_WINDOWS], [],
      [Defined if the target OS is Windows])
  ],
  [AC_MSG_WARN([unsupported system: $host_os])]
)
AM_CONDITIONAL([HOST_WINDOWS], [test "x$OS_VERSION" = "xwindows"])

#autoconf stuff
AM_INIT_AUTOMAKE([foreign -Wall -Werror])
AC_CONFIG_SUBDIRS([src/filext src/buffer src/zlib])
AC_CONFIG_SRCDIR([src/])
AC_CONFIG_HEADERS([config.h])

#program config
AC_PROG_CC
AC_PROG_CXX
AM_PROG_AR
AC_PROG_RANLIB
AC_C_RESTRICT

#user and host info
# none

#headers
# none

#types
AC_TYPE_SIZE_T
AC_TYPE_UINT8_T
AC_TYPE_OFF_T

#functions
AC_FUNC_MALLOC
AC_CHECK_FUNCS([atexit])
AC_CHECK_FUNCS([strerror])
AC_CHECK_FUNCS([strstr])
AC_CHECK_FUNCS([memchr])
AC_CHECK_FUNCS([mkdir])

AC_CONFIG_FILES([
  Makefile
  src/Makefile
])
AC_OUTPUT
