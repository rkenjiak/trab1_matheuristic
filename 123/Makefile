TRACE=NDEBUG
CFLAGS=-D NO_CONFIG_HEADER -D SCIP_VERSION_MAJOR -D$(TRACE) -g -std=c11


bin/mochila: bin/cmain.o bin/probdata_mochila.o bin/problem.o bin/heur_problem.o bin/heur_aleatoria.o bin/heur_gulosa.o
	gcc $(CFLAGS) $(LDFLAGS) -o bin/mochila bin/cmain.o bin/probdata_mochila.o bin/problem.o  bin/heur_problem.o bin/heur_aleatoria.o bin/heur_gulosa.o  -lscip -lm

bin/cmain.o: src/cmain.c
	gcc $(CFLAGS) -c -o bin/cmain.o src/cmain.c

bin/probdata_mochila.o: src/probdata_mochila.c src/probdata_mochila.h
	gcc $(CFLAGS) -c -o bin/probdata_mochila.o src/probdata_mochila.c

bin/problem.o: src/problem.c src/problem.h
	gcc $(CFLAGS) -c -o bin/problem.o src/problem.c

bin/heur_aleatoria.o: src/heur_aleatoria.c src/heur_aleatoria.h
	gcc $(CFLAGS) -c -o bin/heur_aleatoria.o src/heur_aleatoria.c

bin/heur_gulosa.o: src/heur_gulosa.c src/heur_gulosa.h
	gcc $(CFLAGS) -c -o bin/heur_gulosa.o src/heur_gulosa.c

bin/heur_problem.o: src/heur_problem.c src/heur_problem.h
	gcc $(CFLAGS) -c -o bin/heur_problem.o src/heur_problem.c

.PHONY: clean

clean:
	rm -f bin/*.o bin/mochila

