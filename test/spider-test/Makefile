# -*- makefile -*-
TARGET:=spidertest
HEADERS=spidertest.h
SOURCES=spidertest.cpp main.cpp
SOURCES+=$(SRCDIR)/spider/spider.cpp

include ../../config.mk

LIBS+=-lcppunit -lsmbclient -lmysqlpp -ldata_storage -lmagic

.SUFFIXES: .cpp .o

.cpp.o:
	$(CC) $(CFLAGS) $(INCLUDEPATH) $(DEFINES) -fPIC -c -o $@ $<

$(TARGET): $(OBJECTS)
	mkdir -p $(DESTDIR)/test
	$(CC) $(CFLAGS) $(INCLUDEPATH) $(DEFINES) -o $(DESTDIR)/test/spidertest $(OBJECTS) $(LIBS)

clean:
	rm -rf $(DESTDIR)/test/spidertest *.o *.d *.gcov *.gcda *.gcno
