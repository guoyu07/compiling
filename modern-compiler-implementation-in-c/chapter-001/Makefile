VPATH=src:output
OUTPUT_PATH=output
BIN_PATH=bin

CC=gcc

COMPILE_CFLAGS=-O0 -g -c
LINK_CFLAGS=-g

LINK_COMMAND=$(CC) $(LINK_CFLAGS)
COMPILE_COMMAND=$(CC) $(COMPILE_CFLAGS)

install: a.out
	cp $< $(BIN_PATH)/a.out

$(OUTPUT_PATH)/a.out: $(OUTPUT_PATH)/main.o $(OUTPUT_PATH)/prog.o $(OUTPUT_PATH)/slp.o $(OUTPUT_PATH)/util.o $(OUTPUT_PATH)/func.o $(OUTPUT_PATH)/table.o
	$(LINK_COMMAND) $^ -o $@

$(OUTPUT_PATH)/main.o: main.c slp.h util.h func.h table.h
	$(COMPILE_COMMAND) $< -o $@

$(OUTPUT_PATH)/table.o: table.c table.h
	$(COMPILE_COMMAND) $< -o $@

$(OUTPUT_PATH)/func.o: func.c func.h
	$(COMPILE_COMMAND) $< -o $@

$(OUTPUT_PATH)/prog.o: prog.c prog.h
	$(COMPILE_COMMAND) $< -o $@

$(OUTPUT_PATH)/slp.o: slp.c slp.h
	$(COMPILE_COMMAND) $< -o $@

$(OUTPUT_PATH)/util.o: util.c util.h
	$(COMPILE_COMMAND) $< -o $@

clean:
	rm -f output/*
