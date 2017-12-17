FLAGS +=
LDFLAGS += -Cnes.cfg

AS65 ?= ca65
LD65 ?= ld65

ASSEMBLE = $(AS65) $(FLAGS)
LINK = $(LD65) $(LDFLAGS) $(FLAGS)

SOURCES = test.asm
OBJECTS =  $(SOURCES:.asm=.o)

EXECUTABLE = test.nes

.PHONY: all clean

all: $(EXECUTABLE)
clean:
	-rm -v $(OBJECTS) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS) nes.cfg
	$(LINK) -o$@ $<

test.o : test.asm
	$(ASSEMBLE) -o$@ $<
