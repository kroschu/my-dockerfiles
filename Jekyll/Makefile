.PHONY: help build run stop start clean superclean log shell

help:
	@echo "Please use \`make <target>' where <target> is one of"
	@echo "  build				to build a jekyll docker container"
	@echo "  run 				to run pre-built jekyll container"
	@echo "  start  			to start an existing jekyll container"
	@echo "  stop   			to stop an existing jekyll container"
	@echo ""
	@echo "  log      			to see the logs of a running container"
	@echo "  shell      		to execute a shell on jekyll container"
	@echo ""
	@echo "  clean      		to stop and delete jekyll container"
	@echo "  superclean     	to clean and delete jekyll images"

build:
	@docker build -t mmphego/jekyll .

run:
	@docker run --rm --name=jekyll -v "$PWD:/site" -p 4000:4000 mmphego/jekyll

start:
	@docker start mmphego/jekyll || true

stop:
	@docker stop mmphego/jekyll || true

clean: stop
	@docker rm -v -f mmphego/jekyll || true

superclean: clean
	@docker rmi -f mmphego/jekyll || true

log:
	@docker logs -f mmphego/jekyll

shell:
	@docker exec -it mmphego/jekyll bash