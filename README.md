# spring-on-corretto

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
