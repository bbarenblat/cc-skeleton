# configure.ac
# Copyright (C) 2013, 2014 Galois, Inc.
# Copyright (C) 2014 Benjamin Barenblat
#
# This program is free software: you can redistribute it and/or modify it under
# the terms of the GNU General Public License as published by the Free Software
# Foundation, either version 3 of the License, or (at your option) any later
# version.
#
# This program is distributed in the hope that it will be useful, but WITHOUT
# ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
# FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more
# details.
#
# You should have received a copy of the GNU General Public License along with
# this program.  If not, see <http://www.gnu.org/licenses/>.

# Fire up Autoconf.
AC_PREREQ([2.69])
AC_INIT([TODO(bbarenblat): Project name here], [0.0.0], [benjamin@barenblat.name])

# Fire up Automake.
AM_INIT_AUTOMAKE([-Wall -Wno-gnu foreign no-dist-gzip dist-xz subdir-objects])
AC_CONFIG_MACRO_DIR([m4])

# Build quietly by default.
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Build a C++ program.
AC_CONFIG_SRCDIR([config.h.in])
AC_CONFIG_HEADERS([config.h])
AC_PROG_CXX([clang++ g++])
AM_CONDITIONAL([USING_CLANG], [test x$CXX = xclang++])
AM_CONDITIONAL([USING_GCC], [test x$CXX = xg++])
AX_CXX_COMPILE_STDCXX_11([noext], [mandatory])

# Generate Makefile.
AC_CONFIG_FILES([Makefile])

# All done.
AC_OUTPUT
