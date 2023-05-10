APP_NAME := awesome-api
LOG_FILE := $(APP_NAME).log

.PHONY: build
build:
	go build -o $(APP_NAME) .

.PHONY: run
run:
	./$(APP_NAME) > $(LOG_FILE) 2>&1 &

.PHONY: stop
stop:
	kill "$(pgrep $(APP_NAME))"

.PHONY: clean
clean: stop
	rm -f $(APP_NAME) $(LOG_FILE)

.PHONY: test
test:
	curl http://localhost:9999
	curl http://localhost:9999/health

.PHONY: help
help:
	@echo "Available targets:"
	@echo "  build  - Compile the application"
	@echo "  run    - Run the application"
	@echo "  stop   - Stop the application"
	@echo "  clean  - Stop and remove the binary and log file"
	@echo "  test   - Test the application with curl"
