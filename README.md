-# spring-on-corrett1

Spring 2.3 on Amazon Corretto

## Prerequisite

- pack
- mvn with jdk

## Usage

### Download this sample
```
git clone https://github.com/a2-ito/spring-on-corretto.git
cd spring-on-corretto/demo
```

### Build an image
```
mvn spring-boot:build-image
```

### Run a docker image
```
docker run -it -p8080:8080 demo:0.0.1-SNAPSHOT
```

## Create an original builder 

You can create your own builder by editting this toml file.
```
vi spring-on-corretto/builder.toml
```

```
cd spring-on-corretto
pack create-builder itotest/cnb-java-builder-tiny --builder-config builder.toml
```

Push a built image to a public docker registry where you want.
It seems we need to push an image to a publich registry to use it as a builder.

## Reference
https://medium.com/@srinivasan.surprise/unpack-cloud-native-buildpacks-9959b601424b

## Verification

### build console logs
```
[INFO]
[INFO] Results:
[INFO]
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO]
[INFO]
[INFO] --- maven-jar-plugin:3.2.0:jar (default-jar) @ demo ---
[INFO] Building jar: /home/vagrant/spring-on-corretto/demo/target/demo-0.0.1-SNAPSHOT.jar
[INFO]
[INFO] --- spring-boot-maven-plugin:2.3.1.RELEASE:repackage (repackage) @ demo ---
[INFO] Replacing main artifact with repackaged archive
[INFO]
[INFO] <<< spring-boot-maven-plugin:2.3.1.RELEASE:build-image (default-cli) < package @ demo <<<
[INFO]
[INFO]
[INFO] --- spring-boot-maven-plugin:2.3.1.RELEASE:build-image (default-cli) @ demo ---
[INFO] Building image 'docker.io/library/demo:0.0.1-SNAPSHOT'
[INFO]
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 0%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 6%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 12%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 14%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 18%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 21%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 23%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 26%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 30%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 33%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 38%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 42%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 47%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 50%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 52%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 56%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 63%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 63%
[INFO]  > Pulling builder image 'docker.io/a2ito/cnb-java-builder-tiny:latest' 100%
[INFO]  > Pulled builder image 'a2ito/cnb-java-builder-tiny@sha256:8e2a627b6ee61b926546a4daebb0039027b49c1de34155f9635e41f110a8cb59'
[INFO]  > Pulling run image 'docker.io/humourmind/cnb-run:tiny' 0%
[INFO]  > Pulling run image 'docker.io/humourmind/cnb-run:tiny' 37%
[INFO]  > Pulling run image 'docker.io/humourmind/cnb-run:tiny' 73%
[INFO]  > Pulling run image 'docker.io/humourmind/cnb-run:tiny' 100%
[INFO]  > Pulled run image 'humourmind/cnb-run@sha256:9e069f5c33818c2ddec99d16c7501a9775f005e5cb69072f8dc618d6120f5d46'
[INFO]  > Executing lifecycle version v0.7.3
[INFO]  > Using build cache volume 'pack-cache-5cbe5692dbc4.build'
[INFO]
[INFO]  > Running creator
[INFO]     [creator]     ---> DETECTING
[INFO]     [creator]     5 of 15 buildpacks participating
[INFO]     [creator]     paketo-buildpacks/amazon-corretto 1.9.0
[INFO]     [creator]     paketo-buildpacks/executable-jar  1.2.1
[INFO]     [creator]     paketo-buildpacks/apache-tomcat   1.1.1
[INFO]     [creator]     paketo-buildpacks/dist-zip        1.2.1
[INFO]     [creator]     paketo-buildpacks/spring-boot     1.5.1
[INFO]     [creator]     ---> ANALYZING
[INFO]     [creator]     Previous image with name "docker.io/library/demo:0.0.1-SNAPSHOT" not found
[INFO]     [creator]     ---> RESTORING
[INFO]     [creator]     ---> BUILDING
[INFO]     [creator]
[INFO]     [creator]     Paketo Amazon Corretto Buildpack 1.9.0
[INFO]     [creator]       https://github.com/paketo-buildpacks/amazon-corretto
[INFO]     [creator]       Build Configuration:
[INFO]     [creator]         $BP_JVM_VERSION              11.*            the Java version
[INFO]     [creator]       Launch Configuration:
[INFO]     [creator]         $BPL_JVM_HEAD_ROOM           0               the headroom in memory calculation
[INFO]     [creator]         $BPL_JVM_LOADED_CLASS_COUNT  35% of classes  the number of loaded classes in memory calculation
[INFO]     [creator]         $BPL_JVM_THREAD_COUNT        250             the number of threads in memory calculation
[INFO]     [creator]       No valid JRE available, providing matching JDK instead. Using a JDK at runtime has security implications.
[INFO]     [creator]       Corretto JDK 11.0.7: Contributing to layer
[INFO]     [creator]         Downloading from https://corretto.aws/downloads/resources/11.0.7.10.1/amazon-corretto-11.0.7.10.1-linux-x64.tar.gz
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Expanding to /layers/paketo-buildpacks_amazon-corretto/jre
[INFO]     [creator]         Writing env.launch/JAVA_HOME.override
[INFO]     [creator]         Writing env.launch/MALLOC_ARENA_MAX.override
[INFO]     [creator]         Writing profile.d/active-processor-count.sh
[INFO]     [creator]       Memory Calculator 4.0.0: Contributing to layer
[INFO]     [creator]         Downloading from https://github.com/cloudfoundry/java-buildpack-memory-calculator/releases/download/v4.0.0/memory-calculator-4.0.0.tgz
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Expanding to /layers/paketo-buildpacks_amazon-corretto/memory-calculator
[INFO]     [creator]         Writing profile.d/memory-calculator.sh
[INFO]     [creator]       Class Counter: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_amazon-corretto/class-counter
[INFO]     [creator]       JVMKill Agent 1.16.0: Contributing to layer
[INFO]     [creator]         Downloading from https://github.com/cloudfoundry/jvmkill/releases/download/v1.16.0.RELEASE/jvmkill-1.16.0-RELEASE.so
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_amazon-corretto/jvmkill
[INFO]     [creator]         Writing env.launch/JAVA_OPTS.append
[INFO]     [creator]       Link-Local DNS: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_amazon-corretto/link-local-dns
[INFO]     [creator]         Writing profile.d/link-local-dns.sh
[INFO]     [creator]       Java Security Properties: Contributing to layer
[INFO]     [creator]         Writing env.launch/JAVA_OPTS.append
[INFO]     [creator]         Writing env.launch/JAVA_SECURITY_PROPERTIES.override
[INFO]     [creator]       Security Providers Configurer: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_amazon-corretto/security-providers-configurer
[INFO]     [creator]         Writing profile.d/security-providers-classpath.sh
[INFO]     [creator]         Writing profile.d/security-providers-configurer.sh
[INFO]     [creator]       OpenSSL Certificate Loader: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_amazon-corretto/openssl-security-provider
[INFO]     [creator]         Writing profile.d/openssl-certificate-loader.sh
[INFO]     [creator]
[INFO]     [creator]     Paketo Executable JAR Buildpack 1.2.1
[INFO]     [creator]         Writing env/CLASSPATH
[INFO]     [creator]       Process types:
[INFO]     [creator]         executable-jar: java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]         task:           java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]         web:            java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]
[INFO]     [creator]     Paketo Spring Boot Buildpack 1.5.1
[INFO]     [creator]       Image labels:
[INFO]     [creator]         org.opencontainers.image.title
[INFO]     [creator]         org.opencontainers.image.version
[INFO]     [creator]         org.springframework.boot.spring-configuration-metadata.json
[INFO]     [creator]         org.springframework.boot.version
[INFO]     [creator]     ---> EXPORTING
[INFO]     [creator]     Adding layer 'launcher'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:class-counter'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:java-security-properties'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:jre'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:jvmkill'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:link-local-dns'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:memory-calculator'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:openssl-security-provider'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/amazon-corretto:security-providers-configurer'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/executable-jar:class-path'
[INFO]     [creator]     Adding 1/1 app layer(s)
[INFO]     [creator]     Adding layer 'config'
[INFO]     [creator]     *** Images (6f0ee7327060):
[INFO]     [creator]           docker.io/library/demo:0.0.1-SNAPSHOT
[INFO]     [creator]     Adding cache layer 'paketo-buildpacks/executable-jar:class-path'
[INFO]
[INFO] Successfully built image 'docker.io/library/demo:0.0.1-SNAPSHOT'
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  03:13 min
[INFO] Finished at: 2020-07-05T02:47:27Z
[INFO] ------------------------------------------------------------------------
```

### verify env variables
```
$ curl localhost:8080/actuator/env | jq
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  5620    0  5620    0     0   171k      0 --:--:-- --:--:-- --:--:--  171k
{
  "activeProfiles": [],
  "propertySources": [
    {
      "name": "server.ports",
      "properties": {
        "local.server.port": {
          "value": 8080
        }
      }
    },
    {
      "name": "servletContextInitParams",
      "properties": {}
    },
    {
      "name": "systemProperties",
      "properties": {
        "awt.toolkit": {
          "value": "sun.awt.X11.XToolkit"
        },
        "java.specification.version": {
          "value": "11"
        },
        "sun.cpu.isalist": {
          "value": ""
        },
        "sun.jnu.encoding": {
          "value": "ANSI_X3.4-1968"
        },
        "java.class.path": {
          "value": "/workspace"
        },
        "java.vm.vendor": {
          "value": "Amazon.com Inc."
        },
        "sun.arch.data.model": {
          "value": "64"
        },
        "java.vendor.url": {
          "value": "https://aws.amazon.com/corretto/"
        },
        "catalina.useNaming": {
          "value": "false"
        },
        "user.timezone": {
          "value": "GMT"
        },
        "os.name": {
          "value": "Linux"
        },
        "java.vm.specification.version": {
          "value": "11"
        },
        "sun.java.launcher": {
          "value": "SUN_STANDARD"
        },
        "user.country": {
          "value": "US"
        },
        "sun.boot.library.path": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre/lib"
        },
        "sun.java.command": {
          "value": "******"
        },
        "jdk.debug": {
          "value": "release"
        },
        "sun.cpu.endian": {
          "value": "little"
        },
        "user.home": {
          "value": "/root"
        },
        "user.language": {
          "value": "en"
        },
        "java.specification.vendor": {
          "value": "Oracle Corporation"
        },
        "java.security.properties": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/java-security-properties/java-security.properties"
        },
        "java.version.date": {
          "value": "2020-04-14"
        },
        "java.home": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre"
        },
        "file.separator": {
          "value": "/"
        },
        "java.vm.compressedOopsMode": {
          "value": "32-bit"
        },
        "line.separator": {
          "value": "\n"
        },
        "java.specification.name": {
          "value": "Java Platform API Specification"
        },
        "java.vm.specification.vendor": {
          "value": "Oracle Corporation"
        },
        "java.awt.graphicsenv": {
          "value": "sun.awt.X11GraphicsEnvironment"
        },
        "java.awt.headless": {
          "value": "true"
        },
        "sun.management.compiler": {
          "value": "HotSpot 64-Bit Tiered Compilers"
        },
        "java.runtime.version": {
          "value": "11.0.7+10-LTS"
        },
        "user.name": {
          "value": "root"
        },
        "path.separator": {
          "value": ":"
        },
        "os.version": {
          "value": "4.15.0-72-generic"
        },
        "java.runtime.name": {
          "value": "OpenJDK Runtime Environment"
        },
        "file.encoding": {
          "value": "ANSI_X3.4-1968"
        },
        "spring.beaninfo.ignore": {
          "value": "true"
        },
        "java.vm.name": {
          "value": "OpenJDK 64-Bit Server VM"
        },
        "java.vendor.version": {
          "value": "Corretto-11.0.7.10.1"
        },
        "java.vendor.url.bug": {
          "value": "https://github.com/corretto/corretto-11/issues/"
        },
        "java.io.tmpdir": {
          "value": "/tmp"
        },
        "catalina.home": {
          "value": "/tmp/tomcat.7702117743452159176.8080"
        },
        "java.version": {
          "value": "11.0.7"
        },
        "user.dir": {
          "value": "/workspace"
        },
        "os.arch": {
          "value": "amd64"
        },
        "java.vm.specification.name": {
          "value": "Java Virtual Machine Specification"
        },
        "PID": {
          "value": "1"
        },
        "java.awt.printerjob": {
          "value": "sun.print.PSPrinterJob"
        },
        "sun.os.patch.level": {
          "value": "unknown"
        },
        "catalina.base": {
          "value": "/tmp/tomcat.7702117743452159176.8080"
        },
        "java.library.path": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre/lib:/usr/java/packages/lib:/usr/lib64:/lib64:/lib:/usr/lib"
        },
        "java.vendor": {
          "value": "Amazon.com Inc."
        },
        "java.vm.info": {
          "value": "mixed mode"
        },
        "java.vm.version": {
          "value": "11.0.7+10-LTS"
        },
        "sun.io.unicode.encoding": {
          "value": "UnicodeLittle"
        },
        "java.class.version": {
          "value": "55.0"
        }
      }
    },
    {
      "name": "systemEnvironment",
      "properties": {
        "PATH": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/security-providers-configurer/bin:/layers/paketo-buildpacks_amazon-corretto/openssl-security-provider/bin:/layers/paketo-buildpacks_amazon-corretto/memory-calculator/bin:/layers/paketo-buildpacks_amazon-corretto/link-local-dns/bin:/layers/paketo-buildpacks_amazon-corretto/jre/bin:/layers/paketo-buildpacks_amazon-corretto/class-counter/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
          "origin": "System Environment Property \"PATH\""
        },
        "SSL_CERT_FILE": {
          "value": "/etc/ssl/certs/ca-certificates.crt",
          "origin": "System Environment Property \"SSL_CERT_FILE\""
        },
        "JAVA_HOME": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre",
          "origin": "System Environment Property \"JAVA_HOME\""
        },
        "JAVA_OPTS": {
          "value": " -Djava.security.properties=/layers/paketo-buildpacks_amazon-corretto/java-security-properties/java-security.properties -agentpath:/layers/paketo-buildpacks_amazon-corretto/jvmkill/jvmkill-1.16.0-RELEASE.so=printHeapHistogram=1 -XX:ActiveProcessorCount=1 -XX:MaxDirectMemorySize=10M -XX:MaxMetaspaceSize=83696K -XX:ReservedCodeCacheSize=240M -Xss1M -Xmx452879K",
          "origin": "System Environment Property \"JAVA_OPTS\""
        },
        "TERM": {
          "value": "xterm",
          "origin": "System Environment Property \"TERM\""
        },
        "CLASSPATH": {
          "value": "/workspace",
          "origin": "System Environment Property \"CLASSPATH\""
        },
        "HOSTNAME": {
          "value": "babc9c8219a5",
          "origin": "System Environment Property \"HOSTNAME\""
        },
        "LD_LIBRARY_PATH": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre/lib",
          "origin": "System Environment Property \"LD_LIBRARY_PATH\""
        },
        "JAVA_SECURITY_PROPERTIES": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/java-security-properties/java-security.properties",
          "origin": "System Environment Property \"JAVA_SECURITY_PROPERTIES\""
        },
        "PWD": {
          "value": "/workspace",
          "origin": "System Environment Property \"PWD\""
        },
        "SHLVL": {
          "value": "1",
          "origin": "System Environment Property \"SHLVL\""
        },
        "HOME": {
          "value": "/root",
          "origin": "System Environment Property \"HOME\""
        },
        "_": {
          "value": "/layers/paketo-buildpacks_amazon-corretto/jre/bin/java",
          "origin": "System Environment Property \"_\""
        },
        "MALLOC_ARENA_MAX": {
          "value": "2",
          "origin": "System Environment Property \"MALLOC_ARENA_MAX\""
        }
      }
    },
    {
      "name": "applicationConfig: [classpath:/application.properties]",
      "properties": {
        "management.endpoints.enabled-by-default": {
          "value": "true",
          "origin": "class path resource [application.properties]:1:41"
        },
        "management.endpoints.web.exposure.include": {
          "value": "*",
          "origin": "class path resource [application.properties]:2:43"
        }
      }
    }
  ]
}
```
