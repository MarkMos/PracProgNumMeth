CFLAGS += -Wall -O -std=gnu1x `gsl-config --cflags`
LDLIBS += `gsl-config --libs`

results.out: main
	./$< > $@

main: main.o gramschmidtfuncs.o newton.o

clean:
	find . -type f -executable -delete
	rm -f *.o
	rm -f *.out
