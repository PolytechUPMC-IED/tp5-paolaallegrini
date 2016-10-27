
CC = gcc
CFLAGS= -O3 -Wall
LDLIBS= -funroll-loops
COMPILE = $(CC) $(CFLAGS)

all: pbm2png pbm2eps9

pbm2png : pbm2png.c
	$(COMPILE) $(LDLIBS) -s -o pbm2png pbm2png.c -lpng

pbm2eps9 : pbm2eps9.o printer.o
	$(COMPILE) $(LDLIBS) -c -o pbm2eps9.o pbm2eps9.c
	$(COMPILE) $(LDLIBS) -c -o printer.o printer.c
	$(CC) -s -o pbm2eps9 pbm2eps9.o printer.o

pbm2eps9.o : pbm2eps9.c printer.h
	$(CC) -c -o  pbm2eps.o pbm2eps9.c

printer.o : printer.c
	$(CC) -c  -o printer.o printer.c

clean:
	rm -f pbm2png pbm2eps9 pbm2eps9.o printer.o

.PHONY: all clean
