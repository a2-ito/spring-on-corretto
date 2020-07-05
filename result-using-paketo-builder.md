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
[INFO]  > Pulling builder image 'gcr.io/paketo-buildpacks/builder:latest' 100%
[INFO]  > Pulled builder image 'gcr.io/paketo-buildpacks/builder@sha256:0497fcef77e4c54d891366459c7cae9a67ed00ff9a51af4a5cfc2d61866da283'
[INFO]  > Pulling run image 'gcr.io/paketo-buildpacks/run:full-cnb-cf' 100%
[INFO]  > Pulled run image 'gcr.io/paketo-buildpacks/run@sha256:47b284b934fa4bc6b518bac93e019448d5abf232d76419fd193ff63196e77a89'
[INFO]  > Executing lifecycle version v0.8.0
[INFO]  > Using build cache volume 'pack-cache-5cbe5692dbc4.build'
[INFO]
[INFO]  > Running creator
[INFO]     [creator]     ===> DETECTING
[INFO]     [creator]     5 of 15 buildpacks participating
[INFO]     [creator]     paketo-buildpacks/bellsoft-liberica 2.8.0
[INFO]     [creator]     paketo-buildpacks/executable-jar    1.2.7
[INFO]     [creator]     paketo-buildpacks/apache-tomcat     1.3.0
[INFO]     [creator]     paketo-buildpacks/dist-zip          1.3.5
[INFO]     [creator]     paketo-buildpacks/spring-boot       1.9.0
[INFO]     [creator]     ===> ANALYZING
[INFO]     [creator]     Restoring metadata for "paketo-buildpacks/executable-jar:class-path" from app image
[INFO]     [creator]     ===> RESTORING
[INFO]     [creator]     Restoring data for "paketo-buildpacks/executable-jar:class-path" from cache
[INFO]     [creator]     ===> BUILDING
[INFO]     [creator]
[INFO]     [creator]     Paketo BellSoft Liberica Buildpack 2.8.0
[INFO]     [creator]       https://github.com/paketo-buildpacks/bellsoft-liberica
[INFO]     [creator]       Build Configuration:
[INFO]     [creator]         $BP_JVM_VERSION              11.*            the Java version
[INFO]     [creator]       Launch Configuration:
[INFO]     [creator]         $BPL_JVM_HEAD_ROOM           0               the headroom in memory calculation
[INFO]     [creator]         $BPL_JVM_LOADED_CLASS_COUNT  35% of classes  the number of loaded classes in memory calculation
[INFO]     [creator]         $BPL_JVM_THREAD_COUNT        250             the number of threads in memory calculation
[INFO]     [creator]       BellSoft Liberica JRE 11.0.7: Contributing to layer
[INFO]     [creator]         Downloading from https://github.com/bell-sw/Liberica/releases/download/11.0.7+10/bellsoft-jre11.0.7+10-linux-amd64.tar.gz
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Expanding to /layers/paketo-buildpacks_bellsoft-liberica/jre
[INFO]     [creator]         Writing env.launch/JAVA_HOME.override
[INFO]     [creator]         Writing env.launch/MALLOC_ARENA_MAX.override
[INFO]     [creator]         Writing profile.d/active-processor-count.sh
[INFO]     [creator]       Memory Calculator 4.0.0: Contributing to layer
[INFO]     [creator]         Downloading from https://github.com/cloudfoundry/java-buildpack-memory-calculator/releases/download/v4.0.0/memory-calculator-4.0.0.tgz
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Expanding to /layers/paketo-buildpacks_bellsoft-liberica/memory-calculator
[INFO]     [creator]         Writing profile.d/memory-calculator.sh
[INFO]     [creator]       Class Counter: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_bellsoft-liberica/class-counter
[INFO]     [creator]       JVMKill Agent 1.16.0: Contributing to layer
[INFO]     [creator]         Downloading from https://github.com/cloudfoundry/jvmkill/releases/download/v1.16.0.RELEASE/jvmkill-1.16.0-RELEASE.so
[INFO]     [creator]         Verifying checksum
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_bellsoft-liberica/jvmkill
[INFO]     [creator]         Writing env.launch/JAVA_OPTS.append
[INFO]     [creator]       Link-Local DNS: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_bellsoft-liberica/link-local-dns
[INFO]     [creator]         Writing profile.d/link-local-dns.sh
[INFO]     [creator]       Java Security Properties: Contributing to layer
[INFO]     [creator]         Writing env.launch/JAVA_OPTS.append
[INFO]     [creator]         Writing env.launch/JAVA_SECURITY_PROPERTIES.override
[INFO]     [creator]       Security Providers Configurer: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_bellsoft-liberica/security-providers-configurer
[INFO]     [creator]         Writing profile.d/security-providers-classpath.sh
[INFO]     [creator]         Writing profile.d/security-providers-configurer.sh
[INFO]     [creator]       OpenSSL Certificate Loader: Contributing to layer
[INFO]     [creator]         Copying to /layers/paketo-buildpacks_bellsoft-liberica/openssl-security-provider
[INFO]     [creator]         Writing profile.d/openssl-certificate-loader.sh
[INFO]     [creator]
[INFO]     [creator]     Paketo Executable JAR Buildpack 1.2.7
[INFO]     [creator]       https://github.com/paketo-buildpacks/executable-jar
[INFO]     [creator]       Process types:
[INFO]     [creator]         executable-jar: java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]         task:           java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]         web:            java -cp "${CLASSPATH}" ${JAVA_OPTS} org.springframework.boot.loader.JarLauncher
[INFO]     [creator]
[INFO]     [creator]     Paketo Spring Boot Buildpack 1.9.0
[INFO]     [creator]       https://github.com/paketo-buildpacks/spring-boot
[INFO]     [creator]       Build Configuration:
[INFO]     [creator]         $BP_BOOT_NATIVE_IMAGE                  the build to create a native image (requires GraalVM)
[INFO]     [creator]         $BP_BOOT_NATIVE_IMAGE_BUILD_ARGUMENTS  the arguments to pass to the native-image command
[INFO]     [creator]       Web Application Type: Contributing to layer
[INFO]     [creator]         Servlet web application detected
[INFO]     [creator]         Writing env.launch/BPL_JVM_THREAD_COUNT.default
[INFO]     [creator]       Image labels:
[INFO]     [creator]         org.opencontainers.image.title
[INFO]     [creator]         org.opencontainers.image.version
[INFO]     [creator]         org.springframework.boot.spring-configuration-metadata.json
[INFO]     [creator]         org.springframework.boot.version
[INFO]     [creator]     ===> EXPORTING
[INFO]     [creator]     Adding layer 'launcher'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:class-counter'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:java-security-properties'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:jre'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:jvmkill'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:link-local-dns'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:memory-calculator'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:openssl-security-provider'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/bellsoft-liberica:security-providers-configurer'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/executable-jar:class-path'
[INFO]     [creator]     Adding layer 'paketo-buildpacks/spring-boot:web-application-type'
[INFO]     [creator]     Adding 1/1 app layer(s)
[INFO]     [creator]     Adding layer 'config'
[INFO]     [creator]     *** Images (bc5cbeff6f37):
[INFO]     [creator]           docker.io/library/demo:0.0.1-SNAPSHOT
[INFO]     [creator]     Adding cache layer 'paketo-buildpacks/executable-jar:class-path'
[INFO]
[INFO] Successfully built image 'docker.io/library/demo:0.0.1-SNAPSHOT'
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  05:12 min
[INFO] Finished at: 2020-07-05T02:57:29Z
[INFO] ------------------------------------------------------------------------
```
