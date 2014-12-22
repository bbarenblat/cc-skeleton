# Makefile.am
# Copyright (C) 2013, 2014  Galois, Inc.
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

ACLOCAL_AMFLAGS = -I m4

CPPFLAGS = \
	-Wall \
	-D_FORTIFY_SOURCE=2

CXXFLAGS = \
	-std=c++11
	-ftrapv \
	-fstack-protector-strong --param=ssp-buffer-size=4 \
	-fPIE

if USING_CLANG
CXXFLAGS += \
	-Weverything \
	-Wno-c++98-compat
endif USING_CLANG

if USING_GCC
CXXFLAGS += \
	-Wall -Wextra -pedantic \
	-Wformat=2 \
	-Wswitch-default \
	-Wswitch-enum \
	-Wunused -Wunused-parameter -Wunused-but-set-parameter \
	-Wuninitialized -Wmaybe-uninitialized \
	-Wsuggest-attribute=pure -Wsuggest-attribute=const \
		-Wsuggest-attribute=noreturn -Wsuggest-attribute=format \
	-Wtrampolines \
	-Wfloat-equal \
	-Wundef \
	-Wshadow \
	-Wpointer-arith \
	-Wtype-limits \
	-Wcast-qual \
	-Wclobbered \
	-Wconversion -Wsign-conversion \
	-Wlogical-op \
	-Wno-aggressive-loop-optimizations \
	-Wsign-compare \
	-Wmissing-field-initializers \
	-Wpacked \
	-Wredundant-decls \
	-Wstrict-aliasing \
	-Wstrict-overflow \
	-Wabi \
	-Wnoexcept \
	-Wnon-virtual-dtor \
	-Wold-style-cast \
	-Woverloaded-virtual \
	-Wsign-promo \
	-Wzero-as-null-pointer-constant \
	-Wuseless-cast \
	-Wempty-body \
	-fisolate-erroneous-paths-dereference \
	-fisolate-erroneous-paths-attribute \
	-fabi-version=6
endif USING_GCC

LDFLAGS = \
	-Wl,-Bsymbolic-functions \
	-Wl,-z,relro \
	-pie

bin_PROGRAMS = hello            #TODO(bbarenblat): Executable name here
hello_SOURCES = \
	src/main.cc

dist-hook:
	$(RM) `find $(distdir) -type f -name .gitignore`
