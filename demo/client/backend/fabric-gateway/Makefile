# Copyright Intel Corp. All Rights Reserved.
#
# SPDX-License-Identifier: Apache-2.0

TOP = ../../../..
include $(TOP)/build.mk

DOCKER_IMAGE=auction_client_backend

# Note:
# - docker images are not necessarily rebuild if they exist but are outdated.
#   To force rebuild you have two options
#   - do a 'make clobber' first. This ensures you will have the uptodate images
#     but is a broad and slow brush
#   - to just fore rebuilding an image, call `make` with FORCE_REBUILD defined
DOCKER_BUILD_OPTS ?=
ifdef FORCE_REBUILD
	DOCKER_BUILD_OPTS += --no-cache
endif


build: docker

docker:
	# this image is usually built by docker-compose but we still add a
	# convenience target ere until proxy issues with docker-compose are resolved
	$(DOCKER) build $(DOCKER_BUILD_OPTS) -t ${DOCKER_IMAGE} .

clobber:
	IMAGE=$$(${DOCKER} images ${DOCKER_IMAGE} -q); \
        if [ ! -z "$${IMAGE}" ]; then ${DOCKER} rmi ${IMAGE}; fi
	# make clobber in demo/ also would take care but better safe than sorry

