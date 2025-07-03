build:
	docker build -t welo/welomem0:v1.0.0 .
run_local:
	docker run -p 8000:8000 -v $(shell pwd):/app welo/welomem0:v1.0.0 --env-file .env

.PHONY: build run_local
