build:
	docker build -t kompose https://github.com/kubernetes/kompose.git\#main

all: clean build kompose

clean:
	rm -rf kompose

kompose:
	mkdir kompose
	cp docker-compose.yaml kompose/
	docker run --rm -it -v $$PWD/kompose:/opt kompose sh -c "cd /opt && kompose convert -f docker-compose.yaml"

compose_up:
	docker build -t goapp .
	docker-compose up -d