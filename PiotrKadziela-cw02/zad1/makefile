CC=g++
CFLAGS=-c -Wall
OPTLVL=-O0

all: compile compileShared

clean: cleanTest cleanCompile cleanCMake




run: compile
	./bin/out

compile: mainObjFile
	$(CC) -Wall $(OPTLVL) ./bin/main.o -o ./bin/out

mainObjFile: prep main.cpp
	$(CC) $(CFLAGS) $(OPTLVL) main.cpp -o ./bin/main.o





test: compile prepTest
	@echo
	@echo
	@./bin/out @ a ./test/TESTFILE.IN ./test/result/TESTFILE.OUT
	@echo
	@echo
	@echo
	diff ./test/result/TMP ./test/result/TESTFILE.OUT

prep:
	mkdir -p bin/

prepTest:
	mkdir -p ./test/result/
	tr @ a < ./test/TESTFILE.IN > ./test/result/TMP

cleanTest:
	rm -f -r ./test/result/
	
cleanCompile:
	rm -f -r ./bin/

cleanCMake:
	rm -f -r ./out/
	
cleanVS:
	rm -f -r ./.vs/