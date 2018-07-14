# Containerize a [Micronaut](http://micronaut.io/) app with [Jib](https://github.com/GoogleContainerTools/jib)

This is an example of how to easily build a Docker image for a micronaut framework Groovy/Java application with Jib.

Read more about Jib at the [official blog post](https://cloudplatform.googleblog.com/2018/07/introducing-jib-build-java-docker-images-better.html).

## Quickstart

### With Docker

```shell
./gradlew jibDockerBuild

docker run -d -p 8080:8080 micronaut-jib
```
```shell
curl localhost:8080/hello
> Hello World
```

<!-- Dockerize "Hello World" @java @micronautfw app with #Jib -->
Give it a [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Dockerize%20%22Hello%20World%22%20%40java%20%40micronautfw%20app%20with%20%23Jib&url=https://github.com/coollog/micronaut-jib&hashtags=micronaut,jib,java,groovylang,docker,kubernetes,microservices,jib)

### With Kubernetes

```shell
IMAGE=<your image, eg. gcr.io/my-project/micronaut-jib>

./gradlew jib --image=$IMAGE

kubectl run micronaut-jib --image=$IMAGE --port=8080 --restart=Never

# Wait until pod is running
kubectl port-forward micronaut-jib 8080 > /dev/null 2>&1 &
```
```shell
curl localhost:8080/hello
> Hello World
```

<!-- "Hello World" @java @micronautfw app on Kubernetes with #Jib -->
Give it a [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=%22Hello%20World%22%20%40java%20%40micronautfw%20app%20on%20Kubernetes%20with%20%23Jib&url=https://github.com/coollog/micronaut-jib&hashtags=micronaut,jib,java,groovylang,docker,kubernetes,microservices,jib)

## More information

Learn [more about Jib](https://github.com/GoogleContainerTools/jib).
Learn [more about Micronaut](https://micronaut.io).
