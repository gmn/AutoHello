
CC=g++
EXE=hello
CFLAGS=-g -Wall 
INCLUDE=-I/usr/local/include
LIB=-L/usr/local/lib
LINK=-lm
OBJ=hello.o

if HAVE_OLIB
ext_LINK=-lolib
ext_CFLAGS=-DHAVE_OLIB 
else
ext_LINK=
ext_CFLAGS=
endif

CFLAGS+=$(ext_CFLAGS)
LINK+=$(ext_LINK)


.PHONY: all
all: $(EXE)

.PHONY: $(EXE)
$(EXE): $(OBJ)
	$(CC) $^ $(CFLAGS) $(LIB) $(LINK) -o $@

.PHONY: %.o
%.o: %.cpp
	$(CC) $(CFLAGS) $(INCLUDE) -c $^ 

.PHONY:
clean:
	rm -f $(EXE) *.o .gdb_history
