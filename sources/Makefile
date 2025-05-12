#
#	Makefile for sleepwatcher
#
#	21.11.2004 bb	created
#	05.05.2005 bb	removed Carbon framework, target clean added
#	23.04.2006 bb	produce a Universal binary of sleepwatcher
#	02.04.2010 bb	-macosx-version-min=10.3 => 10.4
#	26.12.2018 bb	modified for 64-bit build, PowerPC now optional
#			use "make sleepwatcher" to build the Intel only binary,
#			use "make sleepwatcher.ppc" in a Xcode 3.2.6
#			environment to create the PowerPC binary, then
#			use "make fat" to create a fat binary (PowerPC and
#			Intel 32-bit and 64-bit)
#

CFLAGS_X86_64= -O3 -arch x86_64 
LIBS= -framework IOKit -framework CoreFoundation

BINDIR=/usr/local/sbin
MANDIR=/usr/local/man

sleepwatcher: sleepwatcher.c
	$(CC) $(CFLAGS_X86_64) -o sleepwatcher sleepwatcher.c $(LIBS)

install: sleepwatcher ../sleepwatcher.8
	mkdir -p $(BINDIR)
	install -m 755 sleepwatcher $(BINDIR)
	mkdir -p $(MANDIR)/man8
	install -m 644 ../sleepwatcher.8 $(MANDIR)/man8

clean:
	rm -f sleepwatcher
