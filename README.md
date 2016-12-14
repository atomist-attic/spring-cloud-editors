[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

This [Rug](http://docs.atomist.com/) archive contains editors for [Spring Cloud][spring-cloud] projects.  Take a look inside the
`.atomist` folder.

[spring-cloud]: https://projects.spring.io/spring-cloud/

## Rugs

### AddHystrix

The AddHystrix Editor adds [Hystrix][hystrix] support to an existing [Spring Boot][spring-boot] project.

[spring-boot]: https://projects.spring.io/spring-boot/

#### Prerequisites

Before running this Editor, you must have the following prerequisites
satisfied.

*   A git repository
*   The project must contain a Maven `pom.xml` in its root
*   The project must contain a class annotated with `SpringBootApplication`

#### Parameters

This Editor has no parameters.

#### Running

Run it as follows:

```
$ cd to/your/repo
$ rug edit atomist-rugs:spring-cloud-editors:AddHystrix
```

This will amend your `pom.xml` to include the [Spring Cloud Starter Hystrix][spring-cloud-starter-hystrix] dependency and, if not already present, the [Spring Cloud Dependencies][spring-cloud-dependencies] dependency management section. It will also add the `EnableCircuitBreaker` annotation to the detected class that is annotated with `SpringBootApplication`.

[spring-cloud-starter-hystrix]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-starter-hystrix
[spring-cloud-dependencies]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-dependencies

---
Created by Atomist. Need Help? <a href="https://join.atomist.com/">Join our Slack team</a>
