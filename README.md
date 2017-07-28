# ola
ola microservice using Spring Boot

The detailed instructions to run *Red Hat Helloworld MSA* demo, can be found at the following repository: <https://github.com/redhat-helloworld-msa/helloworld-msa>


Build and Deploy ola locally
----------------------------

1. Open a command prompt and navigate to the root directory of this microservice.
2. Type this command to build and execute the microservice:

        mvn clean compile spring-boot:run

3. The application will be running at the following URL: <http://localhost:8080/api/ola>


Deploy the application in OpenShift
-----------------------------------

1. Make sure to be connected to the Docker Daemon
2. Execute

		mvn clean package docker:build fabric8:json fabric8:apply


ochaloup commands
-----------------

```
  Here we go with
    * `mvn package && oc start-build ola --from-dir=. --follow`

  To check how that works
    * `curl -X GET http://ola-helloworld-msa-restat.192.168.99.100.nip.io/api/ola-chaining`

  Usable commands
    * `oc logs -f `oc get pods | grep ^ola | grep Running | awk '{ print $1 }'``
```

