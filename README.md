# Docker image for jenkins
```
docker run -p 8080:8080 cloudbees/cloudbees-jenkins-distribution:latest
docker run -p 8081:8081 sonatype/nexus3
```
The above command will bring up jenkins which can be access on localhost:8080
and artifactory on localhost:8081

This repo contains a sample java app and jenkinsfile-java to build and push to nexus. 
To build the maven projects you can use plugin: 	
* Maven Integration plugin

To copy file from local to artifactory
```
curl -v -u admin:Cooldude@007 --upload-file dockerfile http://localhost:8083/repository/mip/
```

You can also copy the artifacts to nexus using the Plugin: 
* Artifactory Plugin

To copy artifacts from jenkins/nexus to target VM use Plugin: Publish Over SSH 
https://nozaki.me/roller/kyle/entry/articles-jenkins-sshdeploy

To create your own sample project:
```
mvn archetype:generate -DgroupId=demo -DartifactId=samplewar -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
```

To create sample project in angular js, install node and execute the commands below:
```
npm install -g @angular/cli
ng new my-app
cd my-app
ng serve --open
```

https://jenkins.io/doc/book/pipeline/docker/
https://devopscube.com/docker-containers-as-build-slaves-jenkins/
