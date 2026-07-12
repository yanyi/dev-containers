IMAGE_NAME ?= dev-containers-gleam-elixir
PLATFORM ?= linux/amd64

.PHONY: build latest verify

build: latest

latest verify:
	docker build --platform $(PLATFORM) --pull --tag $(IMAGE_NAME):$@ .
