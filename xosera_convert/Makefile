# xosera_convert - image conversion utility for Xosera
# vim: set noet ts=8 sw=8

# Makefile "best practices" from https://tech.davis-hansson.com/p/make/ (but not forcing gmake)
SHELL := bash
.SHELLFLAGS := -eu -o pipefail -c
.ONESHELL:
.DELETE_ON_ERROR:
MAKEFLAGS += --warn-undefined-variables
MAKEFLAGS += --no-builtin-rules

LDFLAGS		:= $(shell sdl2-config --libs) -lSDL2_image
SDL_CFLAGS	:= $(shell sdl2-config --cflags)

CXXFLAGS	:= -Os -std=c++20 -Wall -Wextra -Werror $(SDL_CFLAGS)

xosera_convert: xosera_convert.cpp lzsa/lzsa

lzsa/lzsa:
	cd lzsa && make all

clean:
	rm -f $(basename $(wildcard *.cpp))
	cd lzsa && make clean

% : %.cpp
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $< -o $@

.PHONY: all clean
