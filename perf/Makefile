# Do *NOT* modify the existing build rules.
# You may add your own rules, e.g., "make run" or "make test".

LAB = perf
STUID=161180162
STUNAME=许致明
include Makefile.git

.PHONY: build submit

build: $(LAB).c
	$(call git_commit, "compile")
	gcc -std=c99 -O1 -Wall -ggdb -o $(LAB) $(LAB).c

submit:
	cd .. && tar cj $(LAB) > submission.tar.bz2
	curl -F "task=M2" -F "id=$(STUID)" -F "name=$(STUNAME)" -F "submission=@../submission.tar.bz2" 114.212.81.90:5000/upload

run: $(LAB).c
	$(call git_commit, "compile")
	gcc -std=c99 -O1 -Wall -ggdb -o $(LAB) $(LAB).c
	./$(LAB)
