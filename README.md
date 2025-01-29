https://spring.io/guides/gs/spring-boot-docker


mvnw clean package

set SPRING_PROFILES_ACTIVE=local
java -jar target\spring-boot-docker-0.0.1-SNAPSHOT.jar

mvnw spring-boot:build-image -Dspring-boot.build-image.imageName=jkarethiya/spring-boot-docker

docker run --name spring-boot-docker -e "SPRING_PROFILES_ACTIVE=local" -p 9080:9080 -t jkarethiya/spring-boot-docker

docker push docker.io/jkarethiya/spring-boot-docker:latest


# docker run -e "JAVA_TOOL_OPTIONS=-agentlib:jdwp=transport=dt_socket,address=8000,server=y,suspend=n" -e "SPRING_PROFILES_ACTIVE=local" -p 9080:9080 -p 8000:8000 -t jkarethiya/spring-boot-docker
# docker run -e "JAVA_OPTS=-Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,server=y,suspend=n" -e "SPRING_PROFILES_ACTIVE=local" -p 9080:9080 -p 8000:8000 -t jkarethiya/spring-boot-docker

docker stop 894572e4258c5311c4d85ef1c562d6b03662e32649e975ccb6bef7cae8716ee2 && docker rm -f 894572e4258c5311c4d85ef1c562d6b03662e32649e975ccb6bef7cae8716ee2

 
 
 docker update --restart no 2cf482b0ddc3bbb6c8b1aea476cc6d0dcdc6b02322053f0f5f2a4e74dd074b6a
