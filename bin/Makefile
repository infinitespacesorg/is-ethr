IMAGE_NAME_AND_TAG = ghcr.io/infinitespacesorg/ethr:latest
PET_NAME = ethr

build:
	docker build --debug --platform linux/arm64,linux/amd64 -f Dockerfile --tag=$(IMAGE_NAME_AND_TAG) .
.PHONY: build

ra: run attach
.PHONY: ra

DOCKER_RUN_ARGS = -p 7100:8888

run:
	docker run --platform linux/amd64 --restart unless-stopped -tid --name $(PET_NAME) $(DOCKER_RUN_ARGS) $(IMAGE_NAME_AND_TAG)
.PHONY: run

attach:
	@docker attach $(PET_NAME)
.PHONY: attach

stop:
	@docker stop $(PET_NAME)
	@docker rm $(PET_NAME)
.PHONY: stop

push:
	docker --debug image push $(IMAGE_NAME_AND_TAG)
.PHONY: push

clean:
	docker image rm -f $(IMAGE_NAME_AND_TAG)
.PHONY: clean