# Introduction

## Usage

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

## 

