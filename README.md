![version](https://img.shields.io/github/v/release/stavshamir/springwolf)
![springwolf-core](https://github.com/stavshamir/springwolf/workflows/springwolf-core/badge.svg)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# Springwolf Core
##### Automated documentation for async APIs built with Spring Boot

### Table Of Contents
- [About](#about)
- [Demo](#demo)
- [Supported protocols](#supported-protocols)
- [Why you should use it](#why-you-should-use-it)
- [Usage](#usage)
- [Example Project](#example-project)

![](screenshot.png)

### About
This project is inspired by [Springfox](https://github.com/springfox/springfox), but instead of documenting REST APIs,
it documents async APIs. 

The resulting document is compliant with the [asyncapi specification](https://www.asyncapi.com/) and is provided as a 
web UI, much like that of Springfox, and allows easy publishing of autogenerated payload examples.

### Demo
You can take a look at a [live demo of springwolf](https://springwolf.github.io/springwolf-ui/).

### Supported protocols
- [Kafka](https://github.com/springwolf/springwolf-kafka)
- SQS (coming soon!)

### Why you should use it
In projects using async APIs, you may often find yourself needing to manually send a message to some topic, whether if you
are manually testing a new feature, debugging or trying to understand some flow. This requires:
1. Instantiating a payload object
2. Serializing your payload object 
3. Publishing it by the CLI or some other interface. 

Springwolf exploits the fact you already fully described your consumer endpoint (with listener annotations, such as 
```@KafkaListner```) and automatically generates an example payload object for the appropriate payload and allows you 
to publish it to the correct channel with a single click.

### Usage
You should not be using this dependency in your application. Instead, use one of the supported protocols plugins:
- [Kafka](https://github.com/springwolf/springwolf-kafka)


### Example Project
You can run the provided [docker-compose](./docker-compose.yml) file and check `localhost:8080/asyncapi-ui.html`.
The source can be found [here](https://github.com/springwolf/springwolf-kafka/tree/master/springwolf-kafka-example).
