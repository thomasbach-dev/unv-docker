UCS_BASE := 5.0-2
UCS_BASE_ERRATA := 528
UCS_TARGET := $(UCS_BASE)-bsb
ERRATA_LEVEL := $(UCS_BASE_ERRATA)

IMAGE_NAME := unv-$(UCS_TARGET)
TARGET_TAG := $(IMAGE_NAME):$(ERRATA_LEVEL)

.PHONY: image

image: build.sh Dockerfile
	docker build \
		--build-arg UCS_BASE=$(UCS_BASE) \
		--build-arg UCS_BASE_ERRATA=$(UCS_BASE_ERRATA) \
		--tag "$(TARGET_TAG)" .
	docker tag "$(TARGET_TAG)" "$(IMAGE_NAME):latest"

build.sh:
	ln -f ../build.sh
