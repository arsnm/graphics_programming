CXX = g++
CC  = gcc

CXXFLAGS = -std=c++17 -O2 -Wall -Wextra
CFLAGS   = -O2 -Wall -Wextra

SRC_CPP = shader_sources.cpp main.cpp
SRC_C   = glad.c
OBJS    = $(SRC_CPP:.cpp=.o) $(SRC_C:.c=.o)

TARGET = main
SHADERS = shader.vert shader.frag

# GLFW paths (adjust per OS)
UNAME_S := $(shell uname -s)

ifeq ($(UNAME_S),Linux)
    GLFW_INCLUDE = ../glfw-3.4/include
    GLFW_LIB = ../glfw-3.4/build/src/libglfw3.a
    SYS_LIBS = -ldl -lm -lGL -lpthread -lwayland-client -lwayland-cursor -lxkbcommon
endif

ifeq ($(UNAME_S),Darwin)
    GLFW_INCLUDE = ../glfw-3.4/include
    GLFW_LIB = ../glfw-3.4/build/src/libglfw3.a
    SYS_LIBS = -framework Cocoa -framework OpenGL -framework IOKit -framework CoreVideo
endif

# Build rules
all: $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(CXXFLAGS) -I$(GLFW_INCLUDE) $(OBJS) $(GLFW_LIB) $(SYS_LIBS) -o $@

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -I$(GLFW_INCLUDE) -c $< -o $@

%.o: %.c
	$(CC) $(CFLAGS) -I$(GLFW_INCLUDE) -c $< -o $@

clean:
	rm -f $(TARGET) $(OBJS)

