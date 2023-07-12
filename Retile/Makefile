CC = gcc
CFLAGS = -Wall -Wextra -O2
LDFLAGS = -lpng -lsqlite3

OBJFILES = gbDB.o gbImage_Geometry.o gbImage_png.o main.o

retile: $(OBJFILES)
	$(CC) $(CFLAGS) -o $@ $^ $(LDFLAGS)

gbDB.o: gbDB.c gbDB.h
	$(CC) $(CFLAGS) -c -o $@ $< 

gbImage_Geometry.o: gbImage_Geometry.c gbImage_Geometry.h NEONvsSSE_5.h
	$(CC) $(CFLAGS) -c -o $@ $< 

gbImage_png.o: gbImage_png.c gbImage_png.h
	$(CC) $(CFLAGS) -c -o $@ $< 

main.o: main.c gbDB.h gbImage_Geometry.h gbImage_png.h
	$(CC) $(CFLAGS) -c -o $@ $< 

.PHONY: clean
clean:
	rm -f *.o retile