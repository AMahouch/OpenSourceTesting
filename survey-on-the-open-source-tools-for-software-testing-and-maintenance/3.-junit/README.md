# 3. JUnit

## Description

JUnit is a simple, open-source framework to write and run repeatable unit tests. Some major features of JUnit include:

* Assertions for checking expected results
* Test fixtures for sharing common test data
* Test runners for automatically running tests

**Why JUnit?**\
There are several benefits to use JUnit for your software testing, including:

* Early fault detection
* Refactoring & regression testing facilitation
* Formal specification for intended behavior

**Sequence**\
Typically, the flow of test generation JUnit works in this sequence:

1. Write the class to be tested
2. Write a test class to test the class under the test
3. Write test setup methods if needed
4. Write test methods which are annotated with @test
5. Write test teardown methods if needed
6. Use a test runner to run the tests



#### Example

The class under the test: **TriangleClassifier.java**, which classifies triangles based on their side lengths as isosceles, scalene, or equilateral.

{% code title="TriangleClassifier.java" %}
```java
public class TriangleClassifier {

    public final static int INVALID = -1;
    public final static int SCALENE = 0;
    public final static int ISOCELES = 1;
    public final static int EQUILATERAL = 2;

    private int side1;
    private int side2;
    private int side3;

    public TriangleClassifier(int side1, int side2, int side3) {
        this.side1 = side1;
        this.side2 = side2;
        this.side3 = side3;
    }

    public int classify () {
        int rval = 0;

        if (side1 <= 0 || side2 <= 0 || side3 <= 0) {
            rval = INVALID;
        }
        if ((side1 + side2 <= side3) || (side1 + side3 <= side2) || (side2 + side3 <= side1)) {
            rval = INVALID;
        }
        if ((side1 != side2) && (side2 != side3) && (side1 != side3)) {
            rval = SCALENE;
        } else if (( side1 == side2) || (side2 == side3) || (side1 == side3)) {
            rval = ISOCELES;
        } else {
            rval = EQUILATERAL;
        }

        return rval;
    }
}
```
{% endcode %}

The test class: **TriangleClassifierTest.java** that contains JUnit test methods.

{% code title="TriangleClassifierTest.java" %}
```java
import org.junit.*;
import org.junit.runner.*;
import org.junit.runners.MethodSorters;
import org.junit.runner.notification.Failure;
import static org.junit.Assert.*;
import java.util.List;

@FixMethodOrder(MethodSorters.NAME_ASCENDING)
public class TriangleClassifierTest {
  
    public static void main (String[] args) {
	Result result = JUnitCore.runClasses (TriangleClassifierTest.class);
	List<Failure> failures = result.getFailures();
	for (Failure failure : failures) {
	    System.out.println(failure);
	    System.out.println(failure.getTrace());
	}
    }
   

    @Before
    public void setUp () {
    }

    @Test
    public void checkInvalid () {
	TriangleClassifier classifier = new TriangleClassifier (3, 4, 8);

        assertEquals(TriangleClassifier.INVALID, classifier.classify ());
    }

    @Test
    public void checkScalene () {
	TriangleClassifier classifier = new TriangleClassifier (4, 5, 6);
        assertEquals(TriangleClassifier.SCALENE, classifier.classify ());
    }

    @Test
    public void checkIsoceles () {
	TriangleClassifier classifier = new TriangleClassifier (3, 3, 4);
        assertEquals(TriangleClassifier.ISOCELES, classifier.classify ());
    }

    @Test
    public void checkEquilateral () {
	TriangleClassifier classifier = new TriangleClassifier (3, 3, 3);
        assertEquals(TriangleClassifier.EQUILATERAL, classifier.classify ());	
    }

    @After
    public void tearDown () {
    }

}
```
{% endcode %}

&#x20;Notice in the test class, the imported packages with their functionalities:

<pre class="language-java" data-full-width="false"><code class="lang-java">import org.junit.*; // core classes and annotations
<strong>import org.junit.runner.*; // classes to run/analyze tests
</strong>import org.junit.runners.MethodSorters; // standard test sorters
import org.junit.runner.notification.Failure; // handles failures
import static org.junit.Assert.*; // static methods for outcome verifcation
</code></pre>

JUnit uses several annotations which are a special form of syntactic meta-data that can be added to Java source code for better code readability and structure. These include `@Test`, `@Before`, `@After`, `@BeforeClass`, and `@Ignore`. The `@FixMethodOrder` tag is used for changing the execution order, in this case by ascending name order.



Junit is commonly used with JaCoCo, an open-source library that measures the code coverage.
