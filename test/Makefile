include ../utils/Makefile.help
include ../utils/Makefile.functions

export NAME := muellerpublic-de

.PHONY: test
test: setup ##@targets Starts docker compose.
	docker-compose -p $(NAME) -f test.yaml up

.PHONY: rm
rm:
	docker-compose -p $(NAME) -f test.yaml rm -f

.PHONY: clean
clean: rm
	sudo rm -rf root

.PHONY: setup
setup:
	for file in html db; do \
	    mkdir -p root/$${file}; \
	    sudo chmod o+rwX root/$${file}; \
	done

.PHONY: count-php-files
count-php-files:
	docker exec test_$(NAME)_1 find /var/www/html -iname \*.php|wc -l

.PHONY: allow-access
allow-access:
	for file in html db; do \
	    sudo chown -R `id -u`.`id -g` root/$${file}; \
	done

.PHONY: setup-permissions
setup-permissions:
	sudo chown -R 33.33 root/html
	sudo chown -R 1001.0 root/db
