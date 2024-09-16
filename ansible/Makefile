VENV ?= $(CURDIR)/.venv
PYTHON ?= python3
SHELL = /bin/bash
MAKEFLAGS += --silent --no-print-directory
.SHELLFLAGS = -ec
.SILENT:

.PHONY: help
help:
	@echo "Environment variables:"
	@echo ""
	@echo "ANSIBLE_OPTS additional flags for Ansible"
	@echo "ANSIBLE_VERBOSITY=3 set the verbosity level for Ansible in molecule tests"
	@echo ""
	@echo "Main targets:"
	@echo ""
	@grep '^## @help' Makefile|cut -d ":" -f 2-3|( (sort|column -s ":" -t) || (sort|tr ":" "\t") || (tr ":" "\t"))

## @help:install-ansible:Install ansible and the dependencies needed in a virtual environment.
.PHONY: install-ansible
install-ansible:
	$(PYTHON) -m venv $(VENV);
	source $(VENV)/bin/activate;\
	$(PYTHON) --version; \
	$(PYTHON) -m pip install -U pip;\
	$(PYTHON) -m pip install --quiet -r $(CURDIR)/requirements.txt --no-compile; \
	ansible-galaxy collection install --upgrade -r $(CURDIR)/requirements.yaml;
	source $(VENV)/bin/activate; \
	ansible-galaxy collection list

## @help:run:Run the Ansible playbook
run: install-ansible
	source $(VENV)/bin/activate;\
	ansible-playbook playbook.yml