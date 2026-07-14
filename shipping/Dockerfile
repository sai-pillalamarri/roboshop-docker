# FROM maven:3.5
# WORKDIR /app
# COPY src ./src
# COPY pom.xml .
# RUN mvn clean package
# RUN mv target/shipping-1.0.jar shipping.jar 
# CMD ["java","-jar","shipping.jar"]

FROM maven:3.9.16 AS builder
WORKDIR /app
COPY src ./src
COPY pom.xml .
RUN mvn clean package
RUN mv target/shipping-1.0.jar shipping.jar

FROM eclipse-temurin:17-jre-alpine
WORKDIR /app
EXPOSE 8080
RUN addgroup -S roboshop && adduser -S -G roboshop roboshop && \
    chown -R roboshop /app
COPY --from=builder /app/target/shipping.jar .
USER roboshop
CMD ["java","-jar","shipping.jar"]

