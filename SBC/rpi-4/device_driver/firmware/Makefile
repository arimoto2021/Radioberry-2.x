CC=gcc
LINK=gcc

OPTIONS=-g -O3 

LIBS=-lrt -lm -lpthread 

COMPILE=$(CC) $(OPTIONS) $(INCLUDES)

PROGRAM=radioberry

SOURCES= \
measure.c \
bias.c \
register.c \
radioberry.c 

HEADERS= \
measure.h \
bias.h \
radioberry.h \
radioberry_ioctl.h \
register.h 

OBJS= \
register.o \
bias.o \
measure.o \
radioberry.o 

all: prebuild $(PROGRAM) $(HEADERS) $(SOURCES) 

prebuild:
	rm -f version.o

$(PROGRAM): $(OBJS) 
	$(LINK) -o $(PROGRAM) $(OBJS) $(LIBS)

.c.o:
	$(COMPILE) -c -o $@ $<


clean:
	-rm -f *.o
	-rm -f $(PROGRAM)
	
install: $(PROGRAM)
	cp $(PROGRAM) /usr/local/bin

