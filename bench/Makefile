CC	:= gcc
CFLAGS	:= -Wall -g -MD -O3 -I../
LDFLAGS := -ldune -lpthread

bench_files := bench_dune bench_dune_ring bench_linux posted_ipi

all: $(bench_files)

bench_dune: bench_dune.o ../libdune/libdune.a
	  $(CC) $(CFLAGS) -static $(<) -L../libdune $(LDFLAGS) -o $(@)

bench_dune_ring: bench_dune_ring.o ../libdune/libdune.a
	$(CC) $(CFLAGS) -static $(<) -L../libdune $(LDFLAGS) -o $(@)

bench_linux: bench_linux.o
	$(CC) $(CFLAGS) $(<) -o $(@)

posted_ipi: posted_ipi.o ../libdune/libdune.a
	  $(CC) $(CFLAGS) -static $(<) -L../libdune $(LDFLAGS) -o $(@)

clean:
	rm -f *.o test *.d $(bench_files)

-include *.d
