# Go 1.17 Docker-Development-Stack
This is a development stack based on Alpine Linux for running Go application in Docker via docker-compose and live reload for Go with air.

### Container
| name          | contains                                        | port     |
|---------------|-------------------------------------------------|----------|
| app           | [golang](https://hub.docker.com/_/golang) 1.17  | 80       |
| mysql         | [mysql](https://hub.docker.com/_/mysql) 8.0     | 3306     |

### Installing
build docker:
```
docker compose build
```
init go project:
```
docker compose run --rm app go mod init locale/app
```
init air setup:
```
docker compose run --rm app air init
```
run app:
```
docker compose up
```

### Check it out
You should now see an output on the console that prints 'Hello World' every second:
```
docker-go-app-1  | Hello World
```

### Sync dependencies issue
Goland IDE uses the systems Go SDK with mod dependencies and not that one in the Docker.
So if you are using the gin or the fiber framework, you have to download it local too:
```
go mod tidy
```

### Thanks a lot to
https://github.com/cosmtrek/air