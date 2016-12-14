[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

This [Rug](http://docs.atomist.com/) archive contains editors for [Spring Cloud][spring-cloud] projects.  Take a look inside the
`.atomist` folder.

[spring-cloud]: https://projects.spring.io/spring-cloud/

## Rugs

### AddHystrix

The AddHystrix Editor adds [Spring Cloud Hystrix][spring-cloud-hystrix] support to an existing [Spring Boot][spring-boot] project.

[spring-cloud-hystrix]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
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


### AddFeign

The AddFeign Editor adds [Spring Cloud Feign][spring-cloud-feign] support to an existing [Spring Boot][spring-boot] project.

[spring-cloud-feign]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
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
$ rug edit atomist-rugs:spring-cloud-editors:AddFeign
```

This will, if not already present, amend your `pom.xml` to include the [Spring Cloud Starter Feign][spring-cloud-starter-feign] dependency and, also if not already present, the [Spring Cloud Dependencies][spring-cloud-dependencies] dependency management section. It will also add the `EnableFeignClients` annotation to the detected class that is annotated with `SpringBootApplication`.

[spring-cloud-starter-feign]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-starter-feign
[spring-cloud-dependencies]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-dependencies


### AddFeignClient

The AddFeignClient Editor adds [Spring Cloud Feign][spring-cloud-feign] support to an existing [Spring Boot][spring-boot] project, including creating a new Feign client interface to consume a microservice.

[spring-cloud-feign]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
[spring-boot]: https://projects.spring.io/spring-boot/

#### Prerequisites

Before running this Editor, you must have the following prerequisites
satisfied.

*   A git repository
*   The project must contain a Maven `pom.xml` in its root
*   The project must contain a class annotated with `SpringBootApplication`

#### Parameters

To run this editor, you must supply the following parameters:

*   `consumed_endpoint_address`: The root address (i.e. http://localhost) or service name (i.e. mymicroservice) of the service being consumed
*   `feign_interface`: The name of the new Feign Java interface
*   `invoking_relative_endpoint_url`: The relative URL to the actual endpoint being invoked on the consumed microservice (i.e. /myendpoint)

#### Running

Run it as follows:

```
$ cd to/your/repo
$ rug edit atomist-rugs:spring-cloud-editors:AddFeignClient /
    consumed_endpoint_address=http://localhost /
    feign_interface=com.myorg.MyFeignClient /
    invoking_relative_endpoint_url=/myendpoint
```

This will, if not already present, amend your `pom.xml` to include the [Spring Cloud Starter Feign][spring-cloud-starter-feign] dependency and, also if not already present, the [Spring Cloud Dependencies][spring-cloud-dependencies] dependency management section. It will also add the `EnableFeignClients` annotation to the detected class that is annotated with `SpringBootApplication`. Finally a new Feign Client Java interface will be generated.

[spring-cloud-starter-feign]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-starter-feign
[spring-cloud-dependencies]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-dependencies


### AddFeignClientWithCircuitBreaker

The AddFeignClientWithCircuitBreaker Editor adds [Spring Cloud Feign][spring-cloud-feign] support, including [Spring Cloud Hystrix][spring-cloud-hystrix], to an existing [Spring Boot][spring-boot] project, creating a new Feign client interface to consume a microservice in the process.

[spring-cloud-feign]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
[spring-cloud-hystrix]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
[spring-boot]: https://projects.spring.io/spring-boot/

#### Prerequisites

Before running this Editor, you must have the following prerequisites
satisfied.

*   A git repository
*   The project must contain a Maven `pom.xml` in its root
*   The project must contain a class annotated with `SpringBootApplication`

#### Parameters

To run this editor, you must supply the following parameters:

*   `consumed_endpoint_address`: The root address (i.e. http://localhost) or service name (i.e. mymicroservice) of the service being consumed
*   `feign_interface`: The name of the new Feign Java interface
*   `invoking_relative_endpoint_url`: The relative URL to the actual endpoint being invoked on the consumed microservice (i.e. /myendpoint)

#### Running

Run it as follows:

```
$ cd to/your/repo
$ rug edit atomist-rugs:spring-cloud-editors:AddFeignClient /
    consumed_endpoint_address=http://localhost /
    feign_interface=com.myorg.MyFeignClient /
    invoking_relative_endpoint_url=/myendpoint
```

This will, if not already present, amend your `pom.xml` to include the [Spring Cloud Starter Feign][spring-cloud-starter-feign] and [Spring Cloud Starter Hystrix][spring-cloud-starter-hystrix] dependencies and, also if not already present, the [Spring Cloud Dependencies][spring-cloud-dependencies] dependency management section. It will also add the `EnableFeignClients` and `EnableCircuitBreaker` annotations to the detected class that is annotated with `SpringBootApplication`. Finally a new Feign Client Java interface will be generated that includes an example of a fallback method for when the circuit breaks.

[spring-cloud-starter-feign]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-starter-feign
[spring-cloud-hystrix]: http://cloud.spring.io/spring-cloud-netflix/spring-cloud-netflix.html
[spring-cloud-dependencies]: https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-dependencies

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com](https://join.atomist.com).

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist-rugs/spring-boot-editors/issues

## Development

You can build, test, and install the project locally with
the [Rug CLI][cli].

[cli]: https://github.com/atomist/rug-cli

```
$ rug test
$ rug install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

[semver]: http://semver.org

```
$ git tag -a 1.2.3
```

The Travis CI build (see badge at the top of this page) will
automatically create a GitHub release using the tag name for the
release and the comment provided on the annotated tag as the contents
of the release notes.  It will also automatically upload the needed
artifacts.

---
Created by Atomist. Need Help? <a href="https://join.atomist.com/">Join our Slack team</a>
