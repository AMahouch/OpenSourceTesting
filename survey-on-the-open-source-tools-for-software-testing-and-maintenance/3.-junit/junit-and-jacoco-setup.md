# JUnit and JaCoCo Setup

JUnit is a popular Java testing framework that simplifies the process of writing and executing unit tests for your Java code. Unit tests are essential for ensuring the correctness of individual components or methods within your codebase. JUnit provides a framework for creating, organizing, and running these tests.

### **Setting Up JUnit in IntelliJ IDEA and Running Tests:**

1. **Download and Install IntelliJ IDEA:**
   * Visit the official IntelliJ IDEA website ([https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/)) and download the Community Edition if you're using it for non-commercial purposes.
   * Follow the installation instructions for your operating system.
2. **Open IntelliJ IDEA:**
   * Launch IntelliJ IDEA after installation.
3. **Create a New Java Project:**
   * Click on "File" > "New" > "Project...".
   * Choose "Java" on the left panel and ensure the "Project SDK" is set to the target machine's installed Java version.
   * Choose the Java language and the Maven build system.
   * Click "Next" and provide a project name (e.g., "CalculatorApp").
   * Click "Finish."
4. **Create Java Classes:**
   * In the Project Explorer on the left, right-click on the "src/main" folder.
   * Select "New" > "Java Class."
   *   Name the class "Calculator" and paste the code for the Calculator class into it.



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
   * In the Project Explorer, right-click on the "src/test" folder.
   * Select "New" > "Java Class."
   *   Name the class "CalculatorTest" and paste the code for the CalculatorTest class into it.

       * Ensure correct JUnit libraries are imported. Documentation can be found here:\
         [https://junit.org/junit5/docs/current/user-guide/](https://junit.org/junit5/docs/current/user-guide/)

       ####

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
5. **Configure Dependencies:**
   * JUnit is used for unit testing, so you need to configure the project to use the JUnit library.
   * Open the project's `pom.xml` file (located in the project root directory) and ensure it contains the JUnit dependencies. The `pom.xml` should match the example provided.
6. **Run CalculatorTest:**
   * In the Project Explorer, right-click on the "CalculatorTest" class.
   * Choose "Run 'CalculatorTest'" to execute the JUnit tests.
7.  **View Test Results:**

    * After running the tests, IntelliJ IDEA will display the test results in the "Run" tool window at the bottom of the screen.
    * Test output (success/failure) should be shown in the window.



{% embed url="https://youtu.be/DmxogNQGhcY" %}

### Setting Up JaCoCo in IntelliJ IDEA

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
