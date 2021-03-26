# shellscript-helloworld
Example of kicking off a shell script in a container

Shows the syntax for adding the script and kicking off with a CMD in the Dockerfile.
The sample is built for scenario where the script is kicking off a Java application and needs a Java 8 runtime.  Two examples of using ibmjava or the Red Hat openjdk base container images.


# Example
Run these commands to create the container
```
cd openjdk
docker build -t helloworld:openjdk .
docker run helloworld:openjdk
```

```sh
❯ cd openjdk
❯ docker build -t helloworld:openjdk .
Sending build context to Docker daemon  3.072kB
Step 1/5 : FROM registry.access.redhat.com/ubi8/openjdk-8
 ---> e7f7cbd09310
Step 2/5 : USER 1001
 ---> Using cache
 ---> 7620d2f7b308
Step 3/5 : COPY --chown=1001:root startENG.sh /work/
 ---> Using cache
 ---> 2d490f18c71f
Step 4/5 : RUN chmod +x /work/startENG.sh
 ---> Using cache
 ---> 160ff1d97f3b
Step 5/5 : CMD ["/bin/bash", "/work/startENG.sh", "Hello World"]
 ---> Using cache
 ---> 06e280f8da5c
Successfully built 06e280f8da5c
Successfully tagged helloworld:openjdk
❯ docker run helloworld:openjdk
Hello World
```
