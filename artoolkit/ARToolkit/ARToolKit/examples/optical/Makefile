INC_DIR= ../../include
LIB_DIR= ../../lib
BIN_DIR= ../../bin

LDFLAG=-L/usr/X11R6/lib -L$(LIB_DIR)
LIBS= -lARgsubUtil -lARgsub -lARvideo -lAR -lglut -lGLU -lGL -lXi -lXmu -lX11 -lm -ljpeg
CFLAG= -O -I/usr/X11R6/include -DUSE_EYETOY -I/usr/src/linux-headers-3.13.0-66-generic/include -I/usr/src/linux-headers-3.13.0-66-generic/arch/x86/include -I$(INC_DIR)

OBJS = object.o draw_object.o
HEADDERS = object.h draw_object.h

all: $(BIN_DIR)/optical

$(BIN_DIR)/optical: optical.o $(OBJS)
	cc -o $(BIN_DIR)/optical optical.o $(OBJS) $(LDFLAG) $(LIBS)

optical.o: optical.c $(HEADDERS)
	cc -c $(CFLAG) optical.c

object.o: object.c $(HEADDERS)
	cc -c $(CFLAG) object.c

draw_object.o: draw_object.c $(HEADDERS)
	cc -c $(CFLAG) draw_object.c

clean:
	rm -f *.o
	rm -f $(BIN_DIR)/optical

allclean:
	rm -f *.o
	rm -f $(BIN_DIR)/optical
	rm -f Makefile
