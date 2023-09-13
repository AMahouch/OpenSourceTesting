# Java Code Coverage (JaCoCo)

{% embed url="https://github.com/AMahouch/JaCoCoDemo/tree/master" fullWidth="true" %}
_all code used can be found at this repository_
{% endembed %}

## Description

\
JaCoCo is an open-source Java code coverage library. It can be used to measure the percentage of code that is executed by tests. JaCoCo can be used to measure line coverage, branch coverage, and method coverage.

JaCoCo works by instrumenting bytecode during runtime. This means that JaCoCo adds additional code to bytecode that tracks which lines of code are executed. JaCoCo can then generate reports that show you which lines of code are covered by your tests and which lines of code are not covered.

While this tool is not specifically used for input space partitioning, it uses the concepts and methodologies of equivalence classes to generate reports.

## Setup

#### Setup Development Environment

* This will be using IntelliJ IDEA integrated development environment (IDE). You can download and install IntelliJ IDEA using documentation from [https://www.jetbrains.com/help/idea/installation-guide.html](https://www.jetbrains.com/help/idea/installation-guide.html).
* You will also need the Java Development Kit (JDK). If not installed, download the latest version from Oracle [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/).
* Finally, this demonstration uses the Maven build automation tool, download instructions found at Apache Maven Project [https://maven.apache.org/install.html](https://maven.apache.org/install.html).

#### Create new Java project

1. Open IntelliJ IDEA.
2. Click on "File" > "New" > "Project..."
3. Choose "Maven" as the project type.
4. Follow the wizard to set up your project. You can choose a group ID, artifact ID, and other project details as needed.
5. Click "Finish" to create the project.

#### Add JaCoCo, Maven, and JUnit as plugins and dependencies

* In `pom.xml` file, add plugins to include JaCoCo and Maven Surefire as such:

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.jacoco</groupId>
            <artifactId>jacoco-maven-plugin</artifactId>
            <version>0.8.10</version> <!-- Update to the version you want to use -->
            <executions>
                <execution>
                    <goals>
                        <goal>prepare-agent</goal>
                    </goals>
                </execution>
                <execution>
                    <id>report</id>
                    <phase>test</phase>
                    <goals>
                        <goal>report</goal>
                    </goals>
                </execution>
            </executions>
            <configuration>
                <dumpOnExit>true</dumpOnExit>
            </configuration>
        </plugin>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-surefire-plugin</artifactId>
            <version>3.1.2</version>
        </plugin>
    </plugins>
</build>
```

* Also, include dependencies for JUnit Jupiter and JaCoCo as such, being sure versions are up-to-date:

```xml
<dependencies>
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-api</artifactId>
        <version>5.10.0</version>
    </dependency>
    <dependency>
        <groupId>org.jacoco</groupId>
        <artifactId>org.jacoco.core</artifactId>
        <version>0.8.10</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

#### Create Calculator class

This setup will be using a simple `Calculator` class that will test a `divide()` program

```java
public class Calculator {
    public int divide(int dividend, int divisor) {
        if (divisor == 0) {
            throw new IllegalArgumentException("Cannot divide by zero");
        }
        return dividend / divisor;
    }
}
```

#### Create test class

Using JUnit framework, create `CalculatorTest` class with imported libraries and test cases:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CalculatorTest {

    @Test
    void testPositiveNumbers() {
        Calculator calculator = new Calculator();
        int result = calculator.divide(10, 2);
        assertEquals(5, result);
    }
    
    // add other test cases here...
}
```

#### Configure run time and generate code coverage report

1. Right-click on your project in IntelliJ IDEA's project explorer.
2. Select "Add Framework Support."
3. Choose "Maven."
4. Click "OK."
5. In the "Run" menu, select "Edit Configurations."
6. Click the "+" button to add a new configuration and select "Maven."
7. In the "Command Line" field, enter `clean test jacoco:report`.
8. Click "Apply" and then "OK" to save the configuration.
9. Right-click on your project again and select "Run" > "Run 'YourProjectName \[clean, test, jacoco:report]'."
10. After the tests run, you'll find the JaCoCo code coverage report in the `target/site/jacoco` directory. Open the HTML report (`index.html`) in your browser to view the code coverage results.

## Demo

{% embed url="https://youtu.be/XcImq-RCh4A" %}



