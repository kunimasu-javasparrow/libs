# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceAudioIn-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x2f940377 0x39b50dc1 0x3a61b8c4 0x566ac433 	\
	0x638add2d

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceAudioIn_stub.a
libSceAudioIn_stub_a_SOURCES = SceAudioIn_stub.S
am_libSceAudioIn_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceAudioIn_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceAudioIn_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceAudioIn_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
