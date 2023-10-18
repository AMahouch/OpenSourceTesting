# Symbolic PathFinder

## Description

[Symbolic Pathfinder (SPF) combines symbolic execution with model checking and constraint solving for automated test case generation and error detection in Java programs with unspecified inputs. In this tool, programs are executed on symbolic inputs representing multiple concrete inputs. Values of variables are represented as constraints generated from the analysis of Java bytecode. The constraints are solved using off-the shelf solvers to generate test inputs guaranteed to achieve complex coverage criteria. SPF has been used successfully at NASA, in academia, and in industry.](#user-content-fn-1)[^1]

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Sample diagram of SPF<br>(source: <a href="https://github.com/SymbolicPathFinder/jpf-symbc/tree/master/doc">https://github.com/SymbolicPathFinder/jpf-symbc/tree/master/doc</a>)</p></figcaption></figure>

## Setup

Ensure Java 8 is installed. Symbolic PathFinder may not work with newer versions of Java.

{% embed url="https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html" %}

SPF developers recommend using the Eclipse Integrated Development Environment.

{% embed url="https://www.eclipse.org/downloads/" %}

**Download JPF Core:**

Download the JPF Core library from one of the following sources:

* [yannicnoller/jpf-core](https://github.com/yannicnoller/jpf-core/tree/0f2f2901cd0ae9833145c38fee57be03da90a64f)
* [corinus/jpf-core](https://github.com/corinus/jpf-core)

**Download JPF Symbolic Extension:**

Download the JPF Symbolic extension from the following source:

* [SymbolicPathFinder/jpf-symbc](https://github.com/SymbolicPathFinder/jpf-symbc)

**Import Projects:** Import both the JPF Core and JPF Symbolic extension as separate Java projects into your Eclipse workspace.

* In Eclipse, go to "File" > "Import" to open the import wizard.
* In the import wizard, select "General" and then "Existing Projects into Workspace."
* Click "Next."
* In the "Select root directory" section, click the "Browse" button and navigate to the directory where you downloaded the Symbolic PathFinder and JPF Core projects. Select the root directory of each project. You should select one project at a time.
* Ensure that the "Copy projects into workspace" option is **unchecked** since you want to work with the projects in their original location.
* Click "Finish."

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

**Create a Configuration File:** Create a `.jpf` directory in your home directory and create a file named `site.properties` within it. This file should contain the following content:

```bash
jpf-core = ${user.home}/.../path-to-jpf-core-folder/jpf-core
jpf-symbc = ${user.home}/.../path-to-jpf-core-folder/jpf-symbc
extensions = ${jpf-core},${jpf-symbc}
```

Ensure to modify the paths to the proper jpf-core and jpf-symbc directory locations.

#### Running

To run Symbolic PathFinder on this program, first create a `.jpf` file with the following content:

```
target = Example.jpf
source = Example.java
```

Then open this `.jpf` file in Eclipse and select the "run-JPF-symbc" run configuration. When running this configuration, Symbolic PathFinder will explore all possible paths through the program.

## Demo

\
Symbolic PathFinder (SPF) outputs a report for each path that it explores. The report will show the following information:

* The path that was explored, including the methods and fields that were accessed.
* The constraints that were generated during the exploration of the path.
* The values that were used for the symbolic inputs.

The report will also indicate whether the path resulted in a bug or error. If so, the report will provide information about the bug or error, such as the type of error and the line of code where the error occurred.

{% embed url="https://youtu.be/4NJW1Q_ASuY?si=3xfd55L-9GcDwU9x&t=892" %}
Corina Pasareanu (CMU, NASA Ames) on "Symbolic Pathfinder".
{% endembed %}

\


[^1]: [https://dl.acm.org/doi/10.1145/1858996.1859035](https://dl.acm.org/doi/10.1145/1858996.1859035)
