# Melissa Email Object Windows C++

CXX=cl
CXXFLAGS=-Zi -EHsc
LDLIBS=mdEmail.lib
RM=del /q /f

all: MelissaEmailObjectWindowsCpp.exe clean

MelissaEmailObjectWindowsCpp.exe:	Main.cpp mdEmail.h mdEnums.h
	$(CXX) $(CXXFLAGS) Main.cpp EmailObject.cpp $(LDLIBS) /Fe:.\Build\MelissaEmailObjectWindowsCpp.exe

clean:
	$(RM) *.obj *.ilk *.pdb *.h.hash *.lib.hash 

