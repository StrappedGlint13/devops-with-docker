# Excercises 

## Excercise 1.1

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/master/images/1.1.png" width="200">

## Excercise 1.2

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/master/images/1.2.png" width="200">

## Excercise 1.3

<img src="https://github.com/StrappedGlint13/devops-with-docker/blob/master/images/1.3.png" width="200">

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



