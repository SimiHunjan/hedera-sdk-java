# Introduction

[![Build Status](https://travis-ci.org/hashgraph/hedera-sdk-java.svg?branch=master)](https://travis-ci.org/hashgraph/hedera-sdk-java) ![Maven](https://img.shields.io/maven-metadata/v/http/central.maven.org/maven2/com/hedera/hashgraph/sdk/maven-metadata.xml.svg) [![License: Apache-2.0](https://img.shields.io/badge/license-Apache--2.0-green)](https://github.com/hashgraph/hedera-sdk-java/blob/master/LICENSE)

> The Java SDK for interacting with [Hedera Hashgraph](https://hedera.com/): the official distributed consensus platform built using the hashgraph consensus algorithm for fast, fair and secure transactions. Hedera enables and empowers developers to build an entirely new class of decentralized applications.

Hedera Hashgraph communicates using [gRPC](https://grpc.io); the Protobufs definitions for the protocol are available in the [hashgraph/hedera-protobuf](https://github.com/hashgraph/hedera-protobuf) repository.

## Usage

### Maven

{% tabs %}
{% tab title="Gradle" %}
```groovy
implementation 'com.hedera.hashgraph:sdk:0.8.1'

// SELECT ONE:
// netty transport (for high throughput applications)
implementation 'io.grpc:grpc-netty-shaded:1.24.0'
// netty transport, unshaded (if you have a matching Netty dependency already)
implementation 'io.grpc:grpc-netty:1.24.0'
// okhttp transport (for lighter-weight applications or Android)
implementation 'io.grpc:grpc-okhttp:1.24.0'
```
{% endtab %}

{% tab title="Maven" %}
```markup
<dependency>
  <groupId>com.hedera.hashgraph</groupId>
  <artifactId>sdk</artifactId>
  <version>0.8.1</version>
</dependency>

<!-- SELECT ONE: -->
<!-- netty transport (for server or desktop applications) -->
<dependency>
  <groupId>io.grpc</groupId>
  <artifactId>grpc-netty-shaded</artifactId>
  <version>1.24.0</version>
</dependency>
<!-- netty transport, unshaded (if you have a matching Netty dependency already) -->
<dependency>
  <groupId>io.grpc</groupId>
  <artifactId>grpc-netty</artifactId>
  <version>1.24.0</version>
</dependency>
<!-- okhttp transport (for lighter-weight applications or Android) -->
<dependency>
  <groupId>io.grpc</groupId>
  <artifactId>grpc-okhttp</artifactId>
  <version>1.24.0</version>
</dependency>
```
{% endtab %}
{% endtabs %}

## Run SDK Examples

### Requirements

1. [ ] IDE of your choice \(IntelliJ/Eclipse\)
2. [ ] Hedera Java SDK
3. [ ] JDK 8

### 1. Download the Java SDK

`git clone https://github.com/hashgraph/hedera-sdk-java.git\`

```text
                                         OR
```

Download the sdk [here](https://github.com/hashgraph/hedera-sdk-java)

### 2. Open the project in your favorite IDE

### 3. Configure your environment variables

* Locate the **env.sample** file in the root directory
* Edit the following variables
  * `NODE_ID`: the ID of a node in the network \(e.g. 0.0.3\)
  * `NODE_ADDRESS`: the IP address and port that corresponds to the node ID \(e.g. 0.testnet.hedera.com:50211\)
  * `OPERATOR`: your `accountId` in the above network \(e.g. 0.0.3\)
  * `OPERATOR_KEY`: the **private key** associated with the operator `accountId`
* Rename the **env.sample** file to **.env**

### 4. Run SDK examples

* Navigate to **/examples/src/main/java/com/hedera/hashgraph/sdk/examples/simple/**
* Run **CreateAccount.java** file

If you have any issues running the examples, please connect with with us via Discord!

