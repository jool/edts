suite  = $(if $(SUITE), suite=$(SUITE), )
REBAR ?= $(shell which rebar 2> /dev/null || which ./rebar)

.PHONY:	all deps check test clean

all: deps
	$(REBAR) compile

deps:
	$(REBAR) get-deps

docs:
	$(REBAR) doc

check:
	$(REBAR) check-plt
	$(REBAR) dialyze

test: eunit ct

eunit:
	$(REBAR) eunit $(suite) skip_deps=true

ct:
	$(REBAR) ct $(suite) skip_deps=true

conf_clean:
	@:

clean:
	$(REBAR) clean
	$(RM) doc/*

# eof
