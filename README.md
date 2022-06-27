# docker-exe2
# commandes à exécuter
```shell
cd docker-exe2/
vim Dockerfile #avec le contenu suivant :
#FROM fabric8/tomcat-9
#ADD webapp.war /opt/tomcat/webapps
docker build -t tomcat:v1 .
docker images
docker history tomcat:v1
docker inspect tomcat:v1
docker run -d -p 20200:8080 --name tomcatcontainer tomcat:v1
docker ps -a
curl http://localhost:20200
cat > result.txt
docker exec -it tomcatcontainer /bin/bash
#à l'intérieur du container
vi /opt/tomcat/conf/tomcat-users.xml
#add (<user username="logwire" password="docker" roles="standard,manager-script" />)
#exit le container
docker image tag tomcat:v1 adnaneadnani/tomcat
docker images
docker push adnaneadnani/tomcat
```