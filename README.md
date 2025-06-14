ULTIMATE GOAL:

################################################################
###   All services started successfully in 117.444 seconds   ###
################################################################

This three command worked for restarting and restarting...

`docker run --name artifactory -v $JFROG_HOME/artifactory/var/:/var/opt/jfrog/artifactory -d -p 8081:8081 -p 8082:8082 releases-docker.jfrog.io/jfrog/artifactory-jcr:7.104.10`

`docker logs -f artifactory`

In case nothing goes as planned (in this accursed world 😄 ifkyk)

`docker stop artifactory && docker rm artifactory`

One more thing which helped me,
In URL the postgress was not working for me. So, I had to write 172.17.0.2 (docker internal network IP).

```bash
shared:
    database:
        driver: org.postgresql.Driver
        type: postgresql
        url: jdbc:postgresql://172.17.0.2:5432/artifactorydb
        username: artifactory
        password: ***
```

So yeah. That's it where I was getting stuck. I recommend not cloning and using this repository.
Follow this => [JFrog Artifactory Installation Link](https://jfrog.com/help/r/jfrog-installation-setup-documentation/install-artifactory-single-node-with-docker)

One more thing,
I have used this docker image -> releases-docker.jfrog.io/jfrog/artifactory-jcr:7.104.10. Here, notice, "jcr" which helped me to use docker as my origin artifact for free.

Thank you
Devarsh
