CXXFLAGS += -std=c++20 -Werror -Wno-unused-parameter

LDLIBS += -lz

ifdef CLANG
    CXX = clang++
    CXXFLAGS += -Weverything -Wno-c++98-compat-pedantic
else
    CXXFLAGS += -Wextra -Wall -Wformat-nonliteral -Wformat-security -Wswitch-default -Wuninitialized \
                -Wfloat-equal -Wundef -Wpointer-arith -Woverloaded-virtual -Wctor-dtor-privacy \
                -Wnon-virtual-dtor -Wsign-promo -Wzero-as-null-pointer-constant -Wstrict-null-sentinel \
                -Wshadow -Wpedantic -Weffc++ -Wsuggest-override
endif

default: ztest
clean:
	rm -rf ztest *.o
