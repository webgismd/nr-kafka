

``` bash
docker rm -f kafka
docker build --tag=kafka:6.1.1 . 
docker image history kafka:6.1.1

docker rm -f zookeeper
docker build --tag=zookeeper:6.1.1 . 
docker image history zookeeper:6.1.1

docker rm -f kafka-rest
docker build --tag=kafka-rest:6.1.1 . 
docker image history kafka-rest:6.1.1

docker rm -f schema-registry
docker build --tag=schema-registry:6.1.1 . 
docker image history schema-registry:6.1.1

docker image ls
```

docker run -it --user 123456:0  -e KAFKA_ZOOKEEPER_CONNECT=localhost:32181 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:29092 -e KAFKA_BROKER_ID=2 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1  kafka:6.1.1


## output example::

``` bash
C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker rm -f kafka
Error: No such container: kafka

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker build --tag=kafka:6.1.1 .
[+] Building 1.8s (6/6) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                                    0.1s 
 => => transferring dockerfile: 32B                                                                                                                                                                                     0.0s 
 => [internal] load .dockerignore                                                                                                                                                                                       0.0s 
 => => transferring context: 2B                                                                                                                                                                                         0.0s 
 => [internal] load metadata for docker.io/confluentinc/cp-zookeeper:6.1.1                                                                                                                                              1.5s 
 => [1/2] FROM docker.io/confluentinc/cp-zookeeper:6.1.1@sha256:dc04584a644b09ec00046a9acd352660b54cd358094a88945802a3444a392586                                                                                        0.0s 
 => CACHED [2/2] RUN set -x &&     chgrp -R 0 /home/appuser && chmod g=u /home/appuser &&     chgrp -R 0 /var/lib && chmod g=u /var/lib                                                                                 0.0s 
 => exporting to image                                                                                                                                                                                                  0.0s 
 => => exporting layers                                                                                                                                                                                                 0.0s 
 => => writing image sha256:f89481ebdaf5dfb5353399b32a295017a32a996147adbc9633f7a19cb624a7f4                                                                                                                            0.0s 
 => => naming to docker.io/library/kafka:6.1.1                                                                                                                                                                          0.0s 

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker image history kafka:6.1.1
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
f89481ebdaf5   3 minutes ago   USER appuser                                    0B        buildkit.dockerfile.v0
<missing>      3 minutes ago   RUN /bin/sh -c set -x &&     chgrp -R 0 /hom…   19.3MB    buildkit.dockerfile.v0
<missing>      3 minutes ago   USER 0                                          0B        buildkit.dockerfile.v0
<missing>      8 days ago      /bin/sh -c #(nop)  CMD ["/etc/confluent/dock…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B        
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   10.9kB
<missing>      8 days ago      /bin/sh -c #(nop)  VOLUME [/var/lib/zookeepe…   0B
<missing>      8 days ago      |6 ARTIFACT_ID=cp-zookeeper BUILD_NUMBER=4 C…   88.3MB
<missing>      8 days ago      /bin/sh -c #(nop)  USER root                    0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV COMPONENT=zookeeper      0B
<missing>      8 days ago      /bin/sh -c #(nop)  EXPOSE 2181 2888 3888        0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PLATFORM_LA…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PACKAGES_RE…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_VERSION        0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=ZooKeeper i…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-zookeeper      0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=a7218c9a       0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=partner-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      8 days ago      /bin/sh -c #(nop) WORKDIR /home/appuser         0B
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B        
<missing>      8 days ago      /bin/sh -c #(nop) COPY file:5dcc52d37b3da1ad…   30B
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   1.9kB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   34.8MB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   189kB     
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   523MB
<missing>      8 days ago      /bin/sh -c #(nop)  ENV PYTHON_VERSION=36-3.6…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV ZULU_OPENJDK=zulu-11-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV CUB_CLASSPATH="/usr/s…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV LANG=C.UTF-8             0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=Common base…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-base-new       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=25cee932       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=tools@co…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      3 weeks ago                                                     4.7kB
<missing>      3 weeks ago                                                     103MB     Imported from -

C:\sw_nt\Git\nr-kafka\docker\zookeeper>
C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker rm -f zookeeper
Error: No such container: zookeeper

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker build --tag=zookeeper:6.1.1 .
[+] Building 1.4s (6/6) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                                    0.1s 
 => => transferring dockerfile: 32B                                                                                                                                                                                     0.0s 
 => [internal] load .dockerignore                                                                                                                                                                                       0.0s 
 => => transferring context: 2B                                                                                                                                                                                         0.0s 
 => [internal] load metadata for docker.io/confluentinc/cp-zookeeper:6.1.1                                                                                                                                              1.2s 
 => [1/2] FROM docker.io/confluentinc/cp-zookeeper:6.1.1@sha256:dc04584a644b09ec00046a9acd352660b54cd358094a88945802a3444a392586                                                                                        0.0s 
 => CACHED [2/2] RUN set -x &&     chgrp -R 0 /home/appuser && chmod g=u /home/appuser &&     chgrp -R 0 /var/lib && chmod g=u /var/lib                                                                                 0.0s 
 => exporting to image                                                                                                                                                                                                  0.0s 
 => => exporting layers                                                                                                                                                                                                 0.0s 
 => => writing image sha256:f89481ebdaf5dfb5353399b32a295017a32a996147adbc9633f7a19cb624a7f4                                                                                                                            0.0s 
 => => naming to docker.io/library/zookeeper:6.1.1                                                                                                                                                                      0.0s 

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker image history zookeeper:6.1.1
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
f89481ebdaf5   3 minutes ago   USER appuser                                    0B        buildkit.dockerfile.v0
<missing>      3 minutes ago   RUN /bin/sh -c set -x &&     chgrp -R 0 /hom…   19.3MB    buildkit.dockerfile.v0
<missing>      3 minutes ago   USER 0                                          0B        buildkit.dockerfile.v0
<missing>      8 days ago      /bin/sh -c #(nop)  CMD ["/etc/confluent/dock…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   10.9kB
<missing>      8 days ago      /bin/sh -c #(nop)  VOLUME [/var/lib/zookeepe…   0B
<missing>      8 days ago      |6 ARTIFACT_ID=cp-zookeeper BUILD_NUMBER=4 C…   88.3MB    
<missing>      8 days ago      /bin/sh -c #(nop)  USER root                    0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV COMPONENT=zookeeper      0B        
<missing>      8 days ago      /bin/sh -c #(nop)  EXPOSE 2181 2888 3888        0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PLATFORM_LA…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PACKAGES_RE…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_VERSION        0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=ZooKeeper i…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-zookeeper      0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=a7218c9a       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=partner-…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      8 days ago      /bin/sh -c #(nop) WORKDIR /home/appuser         0B
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY file:5dcc52d37b3da1ad…   30B
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   0B        
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   1.9kB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   34.8MB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   189kB
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   523MB
<missing>      8 days ago      /bin/sh -c #(nop)  ENV PYTHON_VERSION=36-3.6…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV ZULU_OPENJDK=zulu-11-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV CUB_CLASSPATH="/usr/s…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ENV LANG=C.UTF-8             0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=Common base…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-base-new       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=25cee932       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=tools@co…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      3 weeks ago                                                     4.7kB
<missing>      3 weeks ago                                                     103MB     Imported from -

C:\sw_nt\Git\nr-kafka\docker\zookeeper>
C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker rm -f kafka-rest
Error: No such container: kafka-rest

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker build --tag=kafka-rest:6.1.1 .
[+] Building 1.8s (6/6) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                                    0.0s 
 => => transferring dockerfile: 32B                                                                                                                                                                                     0.0s 
 => [internal] load .dockerignore                                                                                                                                                                                       0.0s 
 => => transferring context: 2B                                                                                                                                                                                         0.0s 
 => [internal] load metadata for docker.io/confluentinc/cp-zookeeper:6.1.1                                                                                                                                              1.5s 
 => [1/2] FROM docker.io/confluentinc/cp-zookeeper:6.1.1@sha256:dc04584a644b09ec00046a9acd352660b54cd358094a88945802a3444a392586                                                                                        0.0s 
 => CACHED [2/2] RUN set -x &&     chgrp -R 0 /home/appuser && chmod g=u /home/appuser &&     chgrp -R 0 /var/lib && chmod g=u /var/lib                                                                                 0.0s 
 => exporting to image                                                                                                                                                                                                  0.1s 
 => => exporting layers                                                                                                                                                                                                 0.0s 
 => => writing image sha256:f89481ebdaf5dfb5353399b32a295017a32a996147adbc9633f7a19cb624a7f4                                                                                                                            0.0s 
 => => naming to docker.io/library/kafka-rest:6.1.1                                                                                                                                                                     0.0s 

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker image history kafka-rest:6.1.1
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
f89481ebdaf5   3 minutes ago   USER appuser                                    0B        buildkit.dockerfile.v0
<missing>      3 minutes ago   RUN /bin/sh -c set -x &&     chgrp -R 0 /hom…   19.3MB    buildkit.dockerfile.v0
<missing>      3 minutes ago   USER 0                                          0B        buildkit.dockerfile.v0
<missing>      8 days ago      /bin/sh -c #(nop)  CMD ["/etc/confluent/dock…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   10.9kB
<missing>      8 days ago      /bin/sh -c #(nop)  VOLUME [/var/lib/zookeepe…   0B
<missing>      8 days ago      |6 ARTIFACT_ID=cp-zookeeper BUILD_NUMBER=4 C…   88.3MB
<missing>      8 days ago      /bin/sh -c #(nop)  USER root                    0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV COMPONENT=zookeeper      0B        
<missing>      8 days ago      /bin/sh -c #(nop)  EXPOSE 2181 2888 3888        0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PLATFORM_LA…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PACKAGES_RE…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_VERSION        0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=ZooKeeper i…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-zookeeper      0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=a7218c9a       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=partner-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      8 days ago      /bin/sh -c #(nop) WORKDIR /home/appuser         0B
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY file:5dcc52d37b3da1ad…   30B       
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   1.9kB     
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   34.8MB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   189kB
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   523MB
<missing>      8 days ago      /bin/sh -c #(nop)  ENV PYTHON_VERSION=36-3.6…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV ZULU_OPENJDK=zulu-11-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV CUB_CLASSPATH="/usr/s…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ENV LANG=C.UTF-8             0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=Common base…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-base-new       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=25cee932       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=tools@co…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      3 weeks ago                                                     4.7kB
<missing>      3 weeks ago                                                     103MB     Imported from -

C:\sw_nt\Git\nr-kafka\docker\zookeeper>
C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker rm -f schema-registry
Error: No such container: schema-registry

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker build --tag=schema-registry:6.1.1 .
[+] Building 2.0s (6/6) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                                    0.1s 
 => => transferring dockerfile: 32B                                                                                                                                                                                     0.0s 
 => [internal] load .dockerignore                                                                                                                                                                                       0.0s 
 => => transferring context: 2B                                                                                                                                                                                         0.0s 
 => [internal] load metadata for docker.io/confluentinc/cp-zookeeper:6.1.1                                                                                                                                              1.7s 
 => [1/2] FROM docker.io/confluentinc/cp-zookeeper:6.1.1@sha256:dc04584a644b09ec00046a9acd352660b54cd358094a88945802a3444a392586                                                                                        0.0s 
 => CACHED [2/2] RUN set -x &&     chgrp -R 0 /home/appuser && chmod g=u /home/appuser &&     chgrp -R 0 /var/lib && chmod g=u /var/lib                                                                                 0.0s 
 => exporting to image                                                                                                                                                                                                  0.1s 
 => => exporting layers                                                                                                                                                                                                 0.0s 
 => => writing image sha256:f89481ebdaf5dfb5353399b32a295017a32a996147adbc9633f7a19cb624a7f4                                                                                                                            0.0s 
 => => naming to docker.io/library/schema-registry:6.1.1                                                                                                                                                                0.0s 

C:\sw_nt\Git\nr-kafka\docker\zookeeper>docker image history schema-registry:6.1.1
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
f89481ebdaf5   4 minutes ago   USER appuser                                    0B        buildkit.dockerfile.v0
<missing>      4 minutes ago   RUN /bin/sh -c set -x &&     chgrp -R 0 /hom…   19.3MB    buildkit.dockerfile.v0
<missing>      4 minutes ago   USER 0                                          0B        buildkit.dockerfile.v0
<missing>      8 days ago      /bin/sh -c #(nop)  CMD ["/etc/confluent/dock…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   10.9kB
<missing>      8 days ago      /bin/sh -c #(nop)  VOLUME [/var/lib/zookeepe…   0B
<missing>      8 days ago      |6 ARTIFACT_ID=cp-zookeeper BUILD_NUMBER=4 C…   88.3MB
<missing>      8 days ago      /bin/sh -c #(nop)  USER root                    0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ENV COMPONENT=zookeeper      0B
<missing>      8 days ago      /bin/sh -c #(nop)  EXPOSE 2181 2888 3888        0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PLATFORM_LA…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_PACKAGES_RE…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG CONFLUENT_VERSION        0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=ZooKeeper i…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-zookeeper      0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=a7218c9a       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=partner-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      8 days ago      /bin/sh -c #(nop) WORKDIR /home/appuser         0B
<missing>      8 days ago      /bin/sh -c #(nop)  USER appuser                 0B
<missing>      8 days ago      /bin/sh -c #(nop) COPY file:5dcc52d37b3da1ad…   30B
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   0B        
<missing>      8 days ago      /bin/sh -c #(nop) COPY --chown=appuser:appus…   1.9kB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   34.8MB
<missing>      8 days ago      /bin/sh -c #(nop) ADD --chown=appuser:appuse…   189kB
<missing>      8 days ago      |4 ARTIFACT_ID=cp-base-new BUILD_NUMBER=4 GI…   523MB
<missing>      8 days ago      /bin/sh -c #(nop)  ENV PYTHON_VERSION=36-3.6…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV ZULU_OPENJDK=zulu-11-…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ENV CUB_CLASSPATH="/usr/s…   0B        
<missing>      8 days ago      /bin/sh -c #(nop)  ENV LANG=C.UTF-8             0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL summary=Common base…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL name=cp-base-new       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL release=6.1.1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL version=25cee932       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL vendor=Confluent       0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL maintainer=tools@co…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG BUILD_NUMBER=-1          0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG GIT_COMMIT               0B
<missing>      8 days ago      /bin/sh -c #(nop)  LABEL io.confluent.docker…   0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG ARTIFACT_ID              0B
<missing>      8 days ago      /bin/sh -c #(nop)  ARG PROJECT_VERSION          0B
<missing>      3 weeks ago                                                     4.7kB
<missing>      3 weeks ago                                                     103MB     Imported from -

docker image ls
REPOSITORY                            TAG       IMAGE ID       CREATED         SIZE
kafka-rest                            6.1.1     f89481ebdaf5   4 minutes ago   769MB
kafka                                 6.1.1     f89481ebdaf5   4 minutes ago   769MB
schema-registry                       6.1.1     f89481ebdaf5   4 minutes ago   769MB
zookeeper                             6.1.1     f89481ebdaf5   4 minutes ago   769MB
registry.redhat.io/rhel8/go-toolset   latest    2cce76bd76d5   3 weeks ago     1.02GB

```


oc create -f buildconfig.yaml
buildconfig.build.openshift.io/cp-kafka created

oc  start-build cp-kafka --follow