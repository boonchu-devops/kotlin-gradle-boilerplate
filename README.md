# Kotlin Gradle Boilerplate code

Boilerplate code for gradle based Kotlin application.

## Links
- [Sample](https://docs.gradle.org/current/samples/sample_building_kotlin_applications.html) Application
- [Jib](https://github.com/GoogleContainerTools/jib/tree/master/jib-gradle-plugin) Plugin

## Features
- Kotlin/JVM 
- Kotlin Coroutine
- Strict Kotlin enable allWarningsAsErrors 
- Unit test with [Spek2](http://spekframework.org/), JUnit 5, [Kluent](https://markusamshove.github.io/Kluent/) and [MockK](https://mockk.io/)
- Static code check using [Detekt](https://github.com/arturbosch/detekt) 
- Code coverage using Jacoco 
- Logging with Logback
- Gradle Kotlin DSL
- Use [jib](https://github.com/GoogleContainerTools/jib/tree/master/examples/spring-boot) to deploy docker image

## Requirements
### Install Java SDK 11
- Use [sdkman](http://sdkman.io/)
```sh
$ curl -s "https://get.sdkman.io" | bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"
$ sdk version
$ sdk install java
```

### Install Gradle 5.3 or higher
```sh
$ sdk update
$ sdk install gradle
```

## Usage
```sh
$ git clone git@github.com:jasoet/kotlin-gradle-boilerplate.git ${YOUR_PROJECT_NAME}
$ cd ${YOUR_PROJECT_NAME}
$ gradle clean build
$ gradle distZip --exclude-task test
$ gradle run
```

## Building and push image with jib
```sh
# deploy docker image
# https://github.com/GoogleContainerTools/jib/tree/master/examples/spring-boot
$ gradle jib --image=boonchu/kotlin-gradle-boilerplate
```

## deploy to k8s
```sh
$ kubectl run kotlin-gradle-boilerplate --image=boonchu/kotlin-gradle-boilerplate --port=8080 --restart=Never
$ k logs kotlin-gradle-boilerplate
17 Jul 2021;22:21:10.455 [main] INFO  id.jasoet.boilerplate.Application - Some Log Message!
Some Random Message!
```
