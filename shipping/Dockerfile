# #
# # Build
# #
# FROM debian:10 AS build

# RUN apt-get update && apt-get -y install maven

# WORKDIR /opt/shipping

# COPY pom.xml /opt/shipping/
# RUN mvn dependency:resolve
# COPY src /opt/shipping/src/
# # mvn package will download the packages and then compile java source and create .jar file
# RUN mvn package 

# #
# # Run
# #
# FROM openjdk:8-jdk

# EXPOSE 8080

# WORKDIR /opt/shipping

# ENV CART_ENDPOINT=cart:8080
# ENV DB_HOST=mysql

# COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

# CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]

FROM debian:10 AS builder
RUN apt-get update && apt-get -y install maven
WORKDIR /opt/shipping
COPY pom.xml /opt/shipping/
RUN mvn dependency:resolve
COPY src /opt/shipping/src/
# This will create jar file inside /opt/shipping
RUN mvn package

FROM openjdk:8-jre-alpine3.9
EXPOSE 8080
WORKDIR /opt/shipping
ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql
COPY --from=builder /opt/shipping/target/shipping-1.0.jar shipping.jar
CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]