REPOSITORY := erwin82
NAME := muellerpublic-de-wordpress
VERSION ?= v1-r1-1

.PHONY: build
build: _build ##@targets Builds the docker image.

.PHONY: clean
clean: _clean ##@targets Removes the local docker image.

.PHONY: deploy
deploy: _deploy ##@targets Deploys the docker image to the repository.

include ../utils/Makefile.help
include ../utils/Makefile.functions
include ../utils/Makefile.image