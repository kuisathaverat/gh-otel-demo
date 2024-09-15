.DEFAULT_GOAL := build
ifdef OTEL_EXPORTER_OTLP_ENDPOINT
export WRAPPER=otel-cli exec --name 'make-subcommand' --tp-print
else
export WRAPPER=
endif

.PHONY: build
build:
	$(WRAPPER) echo build
	$(WRAPPER) sleep 4
	$(WRAPPER) echo 'mock a build'

.PHONY: test
test:
	$(WRAPPER) echo test
	$(WRAPPER) sleep 1
	$(WRAPPER) echo 'mock a test'