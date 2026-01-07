SHELL := /bin/bash
BIN := scrypt vcrypt feistel

.PHONY: all build fix chmod test zip clean quick

all: build

fix:
	@sed -i 's/\r$$//' $(BIN)

chmod: fix
	@chmod u+x $(BIN)

build: chmod
	@echo "Build complete."

test: build
	@set -e; \
	echo "hello" > test; \
	./scrypt password test test.enc; \
	./scrypt password test.enc test2; \
	cmp -s test test2 && echo "cmp: OK"

zip: build
	@rm -f project1.zip
	@zip -q -r project1.zip $(BIN)
	@ls -l project1.zip
	@echo "Created project1.zip"

quick: build
	@set -e; mkdir -p out-scrypt out-vcrypt out-feistel; \
	./scrypt  password samples/test-15.txt out-scrypt/t.scr; \
	./scrypt  password out-scrypt/t.scr out-scrypt/t.dec; \
	cmp -s samples/test-15.txt out-scrypt/t.dec && echo "scrypt OK"; \
	./vcrypt -e password samples/test-16.txt out-vcrypt/t.vc; \
	./vcrypt -d password out-vcrypt/t.vc out-vcrypt/t.dec; \
	cmp -s samples/test-16.txt out-vcrypt/t.dec && echo "vcrypt OK"; \
	./feistel -e password samples/test-41.txt out-feistel/t.fst; \
	./feistel -d password out-feistel/t.fst out-feistel/t.dec; \
	cmp -s samples/test-41.txt out-feistel/t.dec && echo "feistel OK"

clean:
	@rm -f test test.enc test2 project1.zip