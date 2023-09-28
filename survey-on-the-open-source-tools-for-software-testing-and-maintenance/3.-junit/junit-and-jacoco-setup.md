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
   * Name the class "Calculator" and paste the code for the Calculator class into it.
   * In the Project Explorer, right-click on the "src/test" folder.
   * Select "New" > "Java Class."
   * Name the class "CalculatorTest" and paste the code for the CalculatorTest class into it.
     * Ensure correct JUnit libraries are imported. Documentation can be found here:\
       [https://junit.org/junit5/docs/current/user-guide/](https://junit.org/junit5/docs/current/user-guide/)
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
