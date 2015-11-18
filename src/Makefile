all:
	g++ -I ../eigen/ -Ofast -march=native -O4 -Wall -fopenmp -std=c++0x  reps.cc -o reps

run:
	./reps --dim=300 --epohs=20 --model=../work/model --alpha=0.01 --lmda=10000 --edges=../work/edges.sample  --pairs=../work/synonyms


