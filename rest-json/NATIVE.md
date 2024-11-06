# native configuration for module camel-quarkus-fop

I tried the simple example camel-quarkus :

[REST with Jackson](https://github.com/apache/camel-quarkus-examples/tree/main/rest-json)

Both JVM and AOT (Native) version worked.

Adding the module [came-quarkus-fop](https://quarkus.io/extensions/org.apache.camel.quarkus/camel-quarkus-fop/) : 

```shell
quarkus ext add org.apache.camel.quarkus:camel-quarkus-fop
```

And trying the native build :  

```shell
mvn install -Dnative
```

It fails.

Tried on : 

* Ubuntu 24 (Oracle GraalVM 21.0.5 and 23.0.1)
* Mac OS Sequoia (Oracle GraalVM 21.0.5 and 23.0.1)

[Sample build log](build_mac_os_graal23.log)

If seems *camel-quarkus-fop* module is affected by the issue [Fop native failures due to pdfbox 3 upgrade #5244](https://github.com/apache/camel-quarkus/issues/5244).

If it is the case, maybe it should be documented in the [guide](https://camel.apache.org/camel-quarkus/3.15.x/reference/extensions/fop.html).