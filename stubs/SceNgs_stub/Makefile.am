# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceNgs-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x01a52e3a 0x0a92e4ec 0x0a93ea96 0x0d5399cf 	\
	0x0e0acb68 0x0e291aad 0x14ef65a0 0x17a6f564 	\
	0x1af83512 0x1ddbebeb 0x1f51c2ba 0x214485d6 	\
	0x24e909a8 0x251af6a9 0x2a9fa501 0x2f3f7515 	\
	0x3d46d8a7 0x431bf3ab 0x45cf2a73 0x477318c0 	\
	0x4a25bebc 0x4cbe08f3 0x4d705e3e 0x508975bd 	\
	0x534b6e3f 0x54cfb981 0x54ec5b8d 0x5551410d 	\
	0x5add22dc 0x5c71fe09 0x5fd8aedb 0x64d80013 	\
	0x684f080c 0x6ce8b36f 0x793e3e8c 0x79a121d1 	\
	0x8a88e665 0x98703dbc 0x9ab87e71 0x9dcf50f5 	\
	0xa0f5402d 0xa3c807bc 0xaad90deb 0xab6bef8f 	\
	0xafcd824f 0xb307185e 0xb9d971f2 0xbb13373d 	\
	0xbd6f57f0 0xc58298a7 0xc9b8c0b4 0xcd63a2bf 	\
	0xce53bc33 0xd0c9ae5a 0xd124bfb1 0xd668b49c 	\
	0xd7786e99 0xdc7c0f05 0xdd5ca10b 0xe0ac8776 	\
	0xe9b572b7 0xed14cf4a 0xf6b68c31 0xf964120e 	\
	0xfa0a0f34 0xfb8174b1 0xfbe515d4 0xfe1a98e9

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceNgs_stub.a
libSceNgs_stub_a_SOURCES = SceNgs_stub.S
am_libSceNgs_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceNgs_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceNgs_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceNgs_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
