# Excercises 

## Excercise 1.1

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/main/images/1.1.png" width="200">

## Excercise 1.2

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/main/images/1.2.png" width="200">

## Excercise 1.3

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/main/images/1.3.png" width="200">

## Excercise 1.4

```
$ docker run -it ubuntu sh -c 'apt-get update; apt-get install curl; echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
```

## Excercise 1.5

Ubuntu image size is 83MB and Alpine version is only 15.7MB. The functionality is the same:

```
$ docker run -d --name secret fd312adc
0f60215685e1524a041a5330284fa7238445439d402a0188cd218ad994814cce

$ docker exec -it secret sh
/usr/src/app # tail -f ./text.log

2021-09-07 07:19:22 +0000 UTC
2021-09-07 07:19:24 +0000 UTC
2021-09-07 07:19:26 +0000 UTC
2021-09-07 07:19:28 +0000 UTC
2021-09-07 07:19:30 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

## Excercise 1.6

```
$ sudo docker run -it devopsdockeruh/pull_exercise

Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

## Excercise 1.7

Dockerfile:

```
FROM devopsdockeruh/simple-web-service:ubuntu
CMD server
```

Commands:

```
$ docker build . -t web-server
Sending build context to Docker daemon  3.584kB
Step 1/2 : FROM devopsdockeruh/simple-web-service:ubuntu
 ---> 4e3362e907d5
Step 2/2 : CMD server
 ---> Running in 50a8fb101bcb
Removing intermediate container 50a8fb101bcb
 ---> c6391c736812
Successfully built c6391c736812
Successfully tagged web-server:latest

$ docker run web-server
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080
```
