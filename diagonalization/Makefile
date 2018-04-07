CFLAGS += -Wall -O -std=gnu1x `gsl-config --cflags`
LDLIBS += `gsl-config --libs`

.PHONY: all
all: times.txt out.txt times.svg

times.txt: main Makefile
	for n in `seq 73 2 213`; do time --format "$$n %U" --append --output $@ ./main $$n 1>/dev/null; done

out.txt: main
	./$< > $@

main: main.o jacobi.o

times.svg: timeplot.gpi times.txt
	gnuplot $<

clean:
	find . -type f -executable -delete
	rm -f *.o
	rm -f *.txt
	rm -f *.svg