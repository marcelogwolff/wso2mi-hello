FROM maven:3-openjdk-8 AS build
COPY . /usr/src/mymaven
WORKDIR /usr/src/mymaven
RUN mvn clean install

FROM wso2/wso2mi:latest
COPY --from=build /usr/src/mymaven/ESBApp/target/ESBApp_1.0.0.car /home/wso2carbon/wso2mi-1.2.0/repository/deployment/server/carbonapps/ESBApp_1.0.0.car
EXPOSE 9443

