Spring Boot SOAP Server
----------------------------------------------

This repository shows you how to create a basic SOAP server project using [Spring Boot](https://spring.io/projects/spring-boot). Spring Boot SOAP server is based on [Producing a SOAP web service](https://spring.io/guides/gs/producing-web-service/)

#### To Run the Project

```bash
mvn spring-boot:run
```

#### To test the app

Create a `request.xml` file with this content:

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
				  xmlns:gs="http://spring.io/guides/gs-producing-web-service">
   <soapenv:Header/>
   <soapenv:Body>
      <gs:getCountryRequest>
         <gs:name>Spain</gs:name>
      </gs:getCountryRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

Execute this [cURL](https://curl.se/) command

```bash
curl --header "content-type: text/xml" -d @request.xml http://localhost:8080/ws
```