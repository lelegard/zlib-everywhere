CXXFLAGS += -std=c++20 -Werror -Wno-unused-parameter
LDLIBS += -lz

ifeq ($(shell uname -s),Darwin)
    CLANG = 1
endif

ifeq ($(CLANG),))
    CXXFLAGS += -Wextra -Wall -Wformat-nonliteral -Wformat-security -Wswitch-default -Wuninitialized \
                -Wfloat-equal -Wundef -Wpointer-arith -Woverloaded-virtual -Wctor-dtor-privacy \
                -Wnon-virtual-dtor -Wsign-promo -Wzero-as-null-pointer-constant -Wstrict-null-sentinel \
                -Wshadow -Wpedantic -Weffc++ -Wsuggest-override
else
    CXX = clang++
    CXXFLAGS += -Weverything -Wno-c++98-compat-pedantic -Wno-poison-system-directories -Wno-exit-time-destructors \
                -Wno-global-constructors -Wno-padded
endif

default: ztest
clean:
	rm -rf ztest *.o
