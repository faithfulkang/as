# this Makfile is only for the stupid windows platform when update from python34 to anacond3(python36)
# modified from the one generated by python34
TARGET = AS.pyd
OFILES = sipAScmodule.o sipASasdev.o sipAScan.o
HFILES = sipAPIAS.h 

PYVER ?= 36
PYDIR ?= C:/Python$(PYVER)
CC = gcc
CXX = g++
LINK = g++
CPPFLAGS = -DNDEBUG -DUNICODE -DQT_LARGEFILE_SUPPORT -I. -I$(PYDIR)/include
CFLAGS = --std=gnu99 -O2 -Wall
CXXFLAGS = -O2 -Wall
LFLAGS = -mthreads -Wl,-enable-stdcall-fixup -Wl,-enable-auto-import -Wl,-enable-runtime-pseudo-reloc -shared -Wl,-subsystem,windows -Wl,-s
LIBS = -LD:/repository/as/release/aslua/out $(PYDIR)/libs/python$(PYVER).lib -lpyas -laws -lpyas -lpthread -lm -lPCANBasic -lwsock32
LIBS += $(PYDIR)/python$(PYVER).dll
.SUFFIXES: .cpp .cxx .cc .C .c


.cpp.o:
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -o $@ $<

.cc.o:
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -o $@ $<

.cxx.o:
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -o $@ $<

.C.o:
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -o $@ $<

.c.o:
	$(CC) -c $(CFLAGS) $(CPPFLAGS) -o $@ $<

all: $(TARGET)

$(OFILES): $(HFILES)

$(TARGET): $(OFILES)
	$(LINK) $(LFLAGS) -o $(TARGET) $(OFILES) $(LIBS)

clean:
	rm $(TARGET) $(OFILES)
