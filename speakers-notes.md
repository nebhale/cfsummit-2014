# Redis Session Replication
1. `cf push session-application`
1. store/get session
1. `cf restart`
1. get session, **note that session has disappeared**
1. `cf bind-service session-application session-replication`
1. `cf push session-application`
1. store/get session
1. `cf restart`
1. get session, **note that session has survived**

# Packaged Buildpacks
1. `cf buildpacks`
1. `cf create-buildpack test-buildpack ~/Desktop/java-buildpack-abe37f7.zip 0`
1. `cf push test-application -p web-servlet-2-application-1.0.0.BUILD-SNAPSHOT.war -b test-buildpack`, **note that depedencies are downloaded**
1. `cf delete -f test-application`
1. `cf create-buildpack test-offline-buildpack ~/Desktop/java-buildpack-offline-abe37f7.zip 0`
1. `cf push test-application -p web-servlet-2-application-1.0.0.BUILD-SNAPSHOT.war -b test-offline-buildpack`, **note that depedencies are already cached**
