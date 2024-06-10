
PYTHON3CONFIG := $(shell command -v python3-config 2> /dev/null)

ifndef PYTHON3CONFIG
    $(error "python3-config is not available. Please install it. It may be in a python-dev or another package")
endif

CXXFLAGS += -O3 -Wall -shared -std=c++11 -fPIC -fdiagnostics-color
CPPFLAGS += $(shell python -m pybind11 --includes)
LIBNAME = helpers
LIBEXT = $(shell python-config3 --extension-suffix)

default: $(LIBNAME)$(LIBEXT)

%$(LIBEXT): %.cpp
	$(CXX) $(CXXFLAGS) $(CPPFLAGS) $< -o $@
