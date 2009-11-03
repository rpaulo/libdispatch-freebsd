#
#
#

noinst_LTLIBRARIES=libtest.la

libtest_la_SOURCES=			\
	dispatch_test.c

TESTS=					\
	dispatch_after			\
	dispatch_api			\
	dispatch_c99			\
	dispatch_cascade		\
	dispatch_debug			\
	dispatch_group			\
	dispatch_pingpong		\
	dispatch_priority		\
	dispatch_read			\
	dispatch_sema			\
	dispatch_timer_bit31		\
	dispatch_timer_bit63		\
	queue_finalizer

#
# XXX: By broken, we mean non-portable.  We should instead test for the OS
# features they depend on, or port them as required.
#
BROKEN_TESTS=				\
	dispatch_apply			\
	dispatch_cffd			\
	dispatch_drift			\
	dispatch_proc			\
	dispatch_readsync		\
	dispatch_starfish		\
	dispatch_timer_set_time

BROKEN_TOOLS=				\
	harness				\
	nsoperation

noinst_PROGRAMS=$(TESTS)

TOOLS=					\
	summarize

noinst_PROGRAMS+=$(TOOLS)

INCLUDES=-I$(top_builddir) -I$(top_srcdir)
LDADD=libtest.la ../src/libdispatch.la
CFLAGS=-Werror -Wall -DDISPATCH_NO_LEGACY $(MARCH_FLAGS) $(CBLOCKS_FLAGS)
