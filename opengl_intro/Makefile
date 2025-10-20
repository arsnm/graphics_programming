CXX = g++
CXXFLAGS = -std=c++17 -O2 -Wall -Wextra

SRC = shader_sources.cpp glad.c main.cpp
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

# Build
all: $(TARGET)

$(TARGET): $(SRC)
	$(CXX) $(CXXFLAGS) -I$(GLFW_INCLUDE) $^ $(GLFW_LIB) $(SYS_LIBS) -o $@

clean:
	rm -f $(TARGET)

