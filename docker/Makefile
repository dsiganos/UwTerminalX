TAG := dsiganos/uwterminalx$(shell pwd -P):1.0
TAG := `echo $(TAG) | tr A-Z a-z`
VOLUME := $(CURDIR)/..:$(CURDIR)/..

default:
	docker run -it -v $(VOLUME) $(TAG) bash -c "cd $(CURDIR)/.. && qmake UwTerminalX.pro && make clean && make"

shell:
	docker run -it -v $(VOLUME) $(TAG) bash

rootshell:
	docker run -u 0 -it -v $(VOLUME) $(TAG) bash

build:
	docker build --build-arg USER=$(shell whoami) --build-arg UID=$(shell id -u) \
		-t $(TAG) .

.PHONY: default shell build
