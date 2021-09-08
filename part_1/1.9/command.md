Commands:

First I made dirs and text.log file for the bind mount. 

```
docker run -v "$(pwd)/usr/src/app/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```