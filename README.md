# Scalable NestJS (event-driven )

### Starting the app

Install dependencies: \
`npm i`

Pull Redis container: \
`docker pull redis:7-alpine`

Build the application container: \
`DOCKER_BUILDKIT=1 docker build --pull -t scalable-nest -f docker/Dockerfile .`

Start the stack: use Makefile commands

```makefile
start:
	docker-compose up -d

stop:
	docker-compose down

start-issue1:
	docker-compose -f docker-compose-issue1.yml up -d

stop-issue1:
	docker-compose -f docker-compose-issue1.yml down

start-step1:
	docker-compose -f docker-compose-step1.yml up -d

stop-step1:
	docker-compose -f docker-compose-step1.yml down

start-step2:
	docker-compose -f docker-compose-step2.yml up -d

stop-step2:
	docker-compose -f docker-compose-step2.yml down

watch:
	docker logs -f scalable-nest-demo_worker_1

watch-cron:
	docker logs -f scalable-nest-demo_cron_1

monitor:
	npm run start:monitor
```
