# JavaDataFlow

## Description

JavaDataFlow is a Java library that allows you to create data flow graphs from Java input classes. The generated output is a directed graph where a node represents data (e.g. fields, input parameters, etc.) and the edges represent a node influencing the state of another node. This tool can be used to gather all input nodes to a class that can influence the output of a method.



_JavaDataFlow is available under the terms of the Apache License, and code can be found at the following GitHub repository._

{% embed url="https://github.com/daanvdh/JavaDataFlow" %}

## Setup

**Install IntelliJ IDEA**

* This demonstration uses IntelliJ IDEA integrated development environment. This can be downloaded [here](https://www.jetbrains.com/idea/).

**Clone the Project with Git**

* Clone the repository [JavaDataFlowExample](https://github.com/daanvdh/JavaDataFlowExample) through HTTPS in GitHub.
  * This can be in the command line using the `git clone <repository.git>` command
  * This can also be achieved in IntelliJ IDEA: File > New > Project from Version Control

**Load the Maven Build Configuration**

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>In IntelliJ, click the "Load" button in the bottom right of the screen to finish project configuration.</p></figcaption></figure>

**Update Project Paths**

* In `Main.java`, update the 2 strings `systemPath` and `projectPath` to reflect your machine's proper paths:

```java
String systemPath = "/path/to/JavaDataFlowExample/";
String projectPath = "/path/to/JavaDataFlowExample/src/main/java/";
```

## Demo

In the `JavaDataFlowExample`, the example class is used:

```java
public class Example1 {
  int a;

  public int getA() {
    return a;
  }

  public void setA(int inputA) {
    this.a = inputA;
  }
}
```



The code uses the [JavaParser library ](https://javaparser.org/)to initialize a DataFlowGraph object.&#x20;

```java
DataFlowGraph dfg = JavaDataFlow.create(systemPath + projectPath + inputClass);
```
