# vim:set noet ts=4
#
# ibus-table - The Tables engine for IBus
#
# Copyright (c) 2008-2009 Yu Yuwei <acevery@gmail.com>
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this library; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA
#

engine_table_PYTHON = \
	factory.py \
	main.py \
	table.py \
	tabcreatedb.py \
	tabdict.py \
	tabsqlitedb.py \
	speedmeter.py \
	$(NULL)
engine_table_DATA = \
	$(NULL)
engine_tabledir = $(datadir)/ibus-table/engine

bin_SCRIPTS = ibus-table-createdb 

libexec_SCRIPTS = ibus-engine-table

engine_DATA = table.xml
enginedir = $(datadir)/ibus/component

EXTRA_DIST = \
	ibus-table-createdb.in \
	ibus-engine-table.in \
	table.xml.in \
	$(NULL)

CLEANFILES = \
	*.pyc \
	*.pyo \
	ibus-engine-table \
	ibus-table-createdb \
	table.xml \
	$(NULL)

MAINTAINERCLEANFILES = \
	Makefile.in \
	$(NULL)

table.xml: table.xml.in
	( \
		libexecdir=${libexecdir}; \
		pkgdatadir=${pkgdatadir}; \
		s=`cat $<`; \
		eval "echo \"$${s}\""; \
	) > $@

test:
	$(ENV) \
		IBUS_TABLE_LOCATION=$(abs_top_srcdir) \
		DBUS_DEBUG=true \
		LANG=en_US \
		PYTHONPATH=$(abs_top_srcdir) \
		$(PYTHON) $(srcdir)/main.py

