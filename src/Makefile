#####################################################################
# File: Makefile                               Part of Tutorial MUD #
#                                                                   #
# Created by Joachim Pileborg <tm@pileborg.org>                     #
# This file is in the public domain.                                #
#####################################################################

TARGET   = tutorialmud

OBJFILES = main.o logger.o config.o

CXXFLAGS = -Wall -Wextra -std=c++0x -pipe -g
LDFLAGS  = -g

LD       = g++
CXX      = g++

NETLIB   = net/net.a
LIBS     = $(NETLIB)

.PHONY: default
default: all

.PHONY: all
all: $(TARGET)

$(TARGET): $(OBJFILES) $(NETLIB)
	$(LD) $(LDFLAGS) $(OBJFILES) -o $(TARGET) $(LIBS)

.PHONY: $(NETLIB)
$(NETLIB):
	$(MAKE) -C net

.PHONY: clean
clean:
	-rm -f $(OBJFILES)
	-rm -f $(TARGET)

#####################################################################
# Object file targets

main.o: main.cpp tm.h logger.h config.h

logger.o: logger.cpp tm.h logger.h

config.o: config.cpp tm.h config.h
