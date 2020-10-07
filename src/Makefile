CC=gcc
CFLAGS=-O2

OBJ=nss_dev_tld.o

%.o: %.c
	$(CC) -Wall -fPIC -c -o $@ $< $(CFLAGS)

libnss_dev_tld.so.2: $(OBJ)
	$(CC) -shared -o $@ $^ -Wl,-soname,libnss_dev_tld.so.2 $(CFLAGS)

clean:
	rm -f *.o *~ libnss_dev_tld.so.2

install: libnss_dev_tld.so.2
	cp --remove-destination $(CURDIR)/libnss_dev_tld.so.2 /lib

uninstall:
	rm /lib/libnss_dev_tld.so.2
