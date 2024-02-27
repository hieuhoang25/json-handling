# Getting Started

### Reference Documentation
For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.2.2/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.2.2/gradle-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.2.2/reference/htmlsingle/index.html#web)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)

### Intelligent library
- [Jackson](https://javadoc.io/doc/com.google.code.gson/gson/latest/com.google.gson/com/google/gson/Gson.html)
- [Gson](https://javadoc.io/doc/com.fasterxml.jackson.core/jackson-databind/latest/index.html)
### Learn about library
1. Jackson
Jackson is a popular Json processing library in Java. It provides a set of annotations to map Java objects to Json and vice versa. To use Jackson, you need to add the Jackson library to your project.
```xml
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.13.0</version> <!-- Use the latest version available -->
</dependency>
```
Here's a simple example demonstrating JSON parsing and serialization with Jackson:
```java
import com.fasterxml.jackson.databind.ObjectMapper;

public class JsonExample {
    public static void main(String[] args) throws Exception {
        // Creating ObjectMapper instance
        ObjectMapper objectMapper = new ObjectMapper();

        // Serialize Java object to JSON
        MyObject myObject = new MyObject("John Doe", 25);
        String jsonString = objectMapper.writeValueAsString(myObject);
        System.out.println("Serialized JSON: " + jsonString);

        // Deserialize JSON to Java object
        MyObject deserializedObject = objectMapper.readValue(jsonString, MyObject.class);
        System.out.println("Deserialized Object: " + deserializedObject);
    }
}

// Sample Java class
class MyObject {
    private String name;
    private int age;

    // Constructors, getters, setters...

    @Override
    public String toString() {
        return "MyObject{name='" + name + "', age=" + age + '}';
    }
}
```
2. Gson
Gson is another popular Json library for Java developed by Google. It is simple to usse and provides methods for both serialization and deserialization.
```xml
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.9</version> <!-- Use the latest version available -->
</dependency>
```
Here's an example using Gson:
```java
import com.google.gson.Gson;

public class JsonExample {
    public static void main(String[] args) {
        // Creating Gson instance
        Gson gson = new Gson();

        // Serialize Java object to JSON
        MyObject myObject = new MyObject("Jane Doe", 30);
        String jsonString = gson.toJson(myObject);
        System.out.println("Serialized JSON: " + jsonString);

        // Deserialize JSON to Java object
        MyObject deserializedObject = gson.fromJson(jsonString, MyObject.class);
        System.out.println("Deserialized Object: " + deserializedObject);
    }
}

// Sample Java class
class MyObject {
    private String name;
    private int age;

    // Constructors, getters, setters...

    @Override
    public String toString() {
        return "MyObject{name='" + name + "', age=" + age + '}';
    }
}
```
