CXX=g++
CC=gcc
CFLAGS=-O2 -Wall
LDFLAGS=-Llib
PRFFLAGS=-lProof
THRDFLAGS=-lThread
IN=-I$(ROOTSYS)/include/root
INS=-I../../Higgs_CS_and_Width/include
INSS=-I../../Higgs_CS_and_Width/src

CFLAGS += `root-config --cflags`
LIBS += `root-config --glibs`

OBJSS=validationTest.o
OBJSSS=validationTest_pdf.o
OBJSSSS=validationTest_scale.o
OBJSSSSS=validationTest_BR.o

.PHONY: clean all main test

all: validate validatePdf validateScale validateBR

validate: validationTest.o
	$(CXX) -o validationTest.exe $(OBJSS) $(LIBS)

validatePdf: validationTest_pdf.o
	$(CXX) -o validationTest_pdf.exe $(OBJSSS) $(LIBS)

validateScale: validationTest_scale.o
	$(CXX) -o validationTest_scale.exe $(OBJSSSS) $(LIBS)

validateBR: validationTest_BR.o
	$(CXX) -o validationTest_BR.exe $(OBJSSSSS) $(LIBS)

clean:
	@rm *.o *.exe *~ *.txt

new:
	@rm *.root *.eps *.gif *~

##############RULES##############
.cc.o:
	$(CXX) $(CFLAGS) $(IN) $(INS) $(INSS) -c $<
.cpp.o:
	$(CXX) $(CFLAGS) $(IN) $(INS) $(INSS) -c $<


