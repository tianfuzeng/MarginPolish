# Definitions
git_commit ?= $(shell git log --pretty=oneline -n 1 | cut -f1 -d " ")
name = tpesout/margin_polish
version = 1.2.0
tag = ${version}--${git_commit}

# Steps
build:
	# do the docker build
	docker build -t ${name}:${tag} --build-arg git_commit=${git_commit} .
	docker tag ${name}:${tag} ${name}:latest

push: build
	# Requires ~/.dockercfg
	docker push ${name}:${tag}
	docker push ${name}:latest
