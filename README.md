Kogito
------

**Kogito** is the next generation of business automation platform focused on cloud-native development, deployment and execution.

<p align="center"><img width=55% height=55% src="docsimg/kogito.png"></p>

[![GitHub Stars](https://img.shields.io/github/stars/kiegroup/kogito-runtimes.svg)](https://github.com/kiegroup/kogito-runtimes/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/kiegroup/kogito-runtimes.svg)](https://github.com/kiegroup/kogito-runtimes/network/members)
[![GitHub Issues](https://img.shields.io/github/issues/kiegroup/kogito-runtimes.svg)]()
[![Pull Requests](https://img.shields.io/github/issues-pr/kiegroup/kogito-runtimes.svg?style=flat-square)](https://github.com/kiegroup/kogito-runtimes/pulls)
[![Zulip chat](https://img.shields.io/badge/zulip-join_chat-brightgreen.svg)]( https://kie.zulipchat.com)
[![Contributors](https://img.shields.io/github/contributors/kiegroup/kogito-runtimes.svg?style=flat-square)](https://github.com/kiegroup/kogito-runtimes/graphs/contributors)
[![License](https://img.shields.io/github/license/kiegroup/kogito-runtimes.svg)](https://github.com/kiegroup/kogito-runtimes/blob/master/LICENSE)
[![Twitter Follow](https://img.shields.io/twitter/follow/kogito_kie.svg?label=Follow&style=social)](https://twitter.com/kogito_kie?lang=en)

Quick Links
-----------

**Homepage:** http://kogito.kie.org

**Wiki:** https://github.com/kiegroup/kogito-runtimes/wiki

**JIRA:** https://issues.jboss.org/projects/KOGITO

**jBPM:** https://www.jbpm.org/

**Drools:** https://www.drools.org/

Requirements
------------

- [Maven](https://maven.apache.org/) 3.6.2 or later
- [Java](https://openjdk.java.net/install/) 11 or later (devel package)
- optional: Docker installation for running integration tests

Getting Started
---------------

The [Kogito Examples repository](https://github.com/kiegroup/kogito-examples) module contains a number of examples that you can take a look at and try out yourself.
 Please take a look at the readme of each individual example for more details on how the example works and how to run it yourself (either locally or on Kubernetes):
- Process + Quarkus: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/process-quarkus-example/README.md)
- Process + Spring Boot: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/process-springboot-example/README.md)
- Process + Decision + Rules + Quarkus: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/onboarding-example/README.md) - Onboarding example combining one process and two decision services
- Rules + Quarkus: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/rules-quarkus-helloworld/README.md)
- DMN + Quarkus: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/dmn-quarkus-example/README.md)
- Rule Unit + Quarkus: [README.md](https://github.com/kiegroup/kogito-examples/tree/master/ruleunit-quarkus-example/README.md)

Building from source
--------------------

1. Check out the source:

```
git clone git@github.com:kiegroup/kogito-runtimes.git
```

If you don't have a GitHub account use this command instead:

```
git clone https://github.com/kiegroup/kogito-runtimes.git
```

2. Build with Maven:
```
cd kogito-runtimes
mvn clean install -DskipITs
```

3. Run integration tests
The integrations tests are skipped in the command above. To run the tests you need to have docker installed on your machine. To run the tests during the build, just remove the `-DskipITs` argument.
Possible issues - the tests are running docker containers using [testcontainers](https://github.com/testcontainers/testcontainers-java). That by default requires access to the docker.sock file which might result in a security alert on your system and be blocked. In such case you'll see log message similar to 'Can not connect to Ryuk'. In this case do run the tests with following ENV variable set:

```
TESTCONTAINERS_RYUK_DISABLED=true mvn clean verify
```
When the test run is interrupted though, you might end up with docker containers still running, check those using `docker ps` and stop when neccessary.


Contributing to Kogito
--------------------

All contributions are welcome! Before you start please read the [Developing Drools and jBPM](https://github.com/kiegroup/droolsjbpm-build-bootstrap/blob/master/README.md) guide.


Guides
--------------------

Here are some of the most notable ones for quick reference:

- [Quarkus - Using Kogito to add business automation capabilities to an application](https://quarkus.io/guides/kogito-guide) - This guide demonstrates how your Quarkus application can use Kogito to add business automation to power it up with business processes and rules.
- [Quarkus - Getting Started](https://quarkus.io/get-started/) - Quarkus Getting Started guide
