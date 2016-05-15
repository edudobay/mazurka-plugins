PLUGIN_LIBRARY_NAME := mazurka-plugins
PLUGIN_EXT := .so
PLUGIN := $(PLUGIN_LIBRARY_NAME)$(PLUGIN_EXT)

VAMP_SDK_INCLUDE := /usr/include/vamp-sdk
CXXFLAGS := -I $(VAMP_SDK_INCLUDE) -I../include/ -Wall -fPIC -O2
LDFLAGS := -shared -Wl,-soname=$(PLUGIN) -lvamp-sdk -lfftw3

PLUGIN_SOURCES := MazurkaPlugin.cpp MzChronogram.cpp MzPitchPower.cpp MzSilenceFinder.cpp MzSpectrogramClient.cpp MzSummation.cpp \
	MazurkaTransformer.cpp  MzHarmonicSpectrum.cpp  MzPowerCurve.cpp  MzSpectralFlatness.cpp  MzSpectrogramFFTW.cpp \
	MazurkaWindower.cpp     MzNevermore.cpp         MzPowerscape.cpp  MzSpectralFlux.cpp      MzSpectrogramHost.cpp \
	plugins.cpp

PLUGIN_OBJECTS := $(PLUGIN_SOURCES:.cpp=.o)
PLUGIN_OBJECTS := $(PLUGIN_OBJECTS:.c=.o)

$(PLUGIN): $(PLUGIN_OBJECTS)
	$(CXX) -o $@ $^ $(LDFLAGS)
plugins.cpp:
	./makepluginscpp > plugins.cpp
clean:
	rm plugins.cpp
	rm -f *.o *.so
