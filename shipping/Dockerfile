FROM maven:3.5
WORKDIR /app
COPY src ./src
COPY pom.xml .
RUN mvn clean package
RUN mv target/shipping-1.0.jar shipping.jar 
CMD ["java","-jar","shipping.jar"]