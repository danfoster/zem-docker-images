# import deploy config
# You can change the default deploy config with `make cnf="deploy_special.env" release`
dpl ?= deploy.env
include $(dpl)
export $(shell sed 's/=.*//' $(dpl))


# HELP
# This will output the help for each task
# thanks to https://marmelab.com/blog/2016/02/29/auto-documented-makefile.html
.PHONY: help

help: ## This help.
	@awk 'BEGIN {FS = ":.*?## "} /^[a-zA-Z_-]+:.*?## / {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}' $(MAKEFILE_LIST)

.DEFAULT_GOAL := help


# DOCKER TASKS
# Build the container
build: ## Build the container
	docker build -t $(TAG)   --platform linux/amd64,linux/arm64 .

# Can't use multi-platform build with --load, so have a different target for local testing
# https://docs.docker.com/build/building/multi-platform/#prerequisites
load:
	docker build -t $(TAG)  --load .

run: ## Run container on port configured in `config.env`
	docker run -i -t --rm $(TAG)

push: ## Push to dockerhub
	docker push $(TAG)
