# Spring Core - Load Country from Spring Configuration XML

## Objective

This project demonstrates how to configure and load a Spring Bean using an XML configuration file. A `Country` bean is defined in `country.xml`, loaded into the Spring IoC Container, and accessed using `ApplicationContext`.

---

# Technologies Used

- Java 17
- Spring Framework
- Spring Core
- Maven
- SLF4J Logging

---

# Project Structure

```text
spring-learn
│
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── cognizant
│   │   │           └── springlearn
│   │   │               ├── Country.java
│   │   │               └── SpringLearnApplication.java
│   │   │
│   │   └── resources
│   │       ├── application.properties
│   │       └── country.xml
│   │
│   └── test
│
└── pom.xml
```

---

# Country Details

| Code | Country |
|------|---------|
| US | United States |
| DE | Germany |
| IN | India |
| JP | Japan |

In this project, the configured country is:

- **Code:** IN
- **Name:** India

---

# Files Used

## Country.java

Represents the Country bean with:

- Instance variables (`code` and `name`)
- Default constructor
- Getters and Setters
- `toString()` method
- Debug logging

## country.xml

Defines the Spring Bean.

```xml
<bean id="country" class="com.cognizant.springlearn.Country">
    <property name="code" value="IN"/>
    <property name="name" value="India"/>
</bean>
```

## SpringLearnApplication.java

- Loads the Spring XML configuration.
- Retrieves the Country bean.
- Displays the country details using the logger.

## application.properties

Enables debug logging.

```properties
logging.level.com.cognizant.springlearn=DEBUG
```

---

# How It Works

1. Spring loads `country.xml`.
2. The IoC Container creates the `Country` object.
3. The default constructor is invoked.
4. Property values are injected using setter methods.
5. The bean is stored in the Spring Container.
6. `context.getBean()` returns the configured bean.
7. The application displays the country details.

---

# Sample Output

```text
INFO  START

DEBUG Inside Country Constructor.

DEBUG Inside setCode()

DEBUG Inside setName()

DEBUG Country : Country [code=IN, name=India]

INFO END
```

---

# Spring Concepts Covered

## Bean

A bean is an object that is created and managed by the Spring IoC Container.

## bean Tag

Defines a bean in the Spring XML configuration.

## id Attribute

Provides a unique identifier for the bean.

Example:

```xml
id="country"
```

## class Attribute

Specifies the fully qualified Java class of the bean.

Example:

```xml
class="com.cognizant.springlearn.Country"
```

## property Tag

Injects values into bean properties.

Example:

```xml
<property name="code" value="IN"/>
```

## ApplicationContext

The central interface of the Spring IoC Container that manages beans and their lifecycle.

## ClassPathXmlApplicationContext

Loads the XML configuration file from the application's classpath.

## context.getBean()

When `context.getBean("country", Country.class)` is invoked, Spring:

1. Reads the XML configuration.
2. Finds the bean definition.
3. Creates the object.
4. Calls the constructor.
5. Injects property values.
6. Returns the fully initialized bean.

---

# Learning Outcomes

- Spring XML Configuration
- Spring IoC Container
- Bean Creation
- Dependency Injection using XML
- ApplicationContext
- ClassPathXmlApplicationContext
- SLF4J Logging
- Maven Project Structure

---

# Conclusion

This project demonstrates the fundamentals of Spring Core by creating and configuring a bean using an XML configuration file. It provides an understanding of Spring's IoC Container, bean lifecycle, dependency injection, and XML-based configuration.
